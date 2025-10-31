Today we will be practicing on fixing repositories. It is not a universal approach, we should tailor it for our own repository, but it's filled with useful method and commands to mold our repository to what we want it to be.

On the courses page, in the repository evaluation page, you will find a plethora of useful methods to bring your repository up to standard with the course.

First, let's get to a repository. Given we have already generated an ssh key and added it to our repository online, we may clone our repository.
The first thing we want to do is list our repository graph using `git ll`.
If we want to start doing anything from the protected main branch, we usually want to branch off of it and work on it. In the example of `PA1`, each branch will be a homework. 
We start creating commit after commit in the branch.
In this, we are in a branch under a certain name, which we created locally, we will be pushing it to the remote repository and an upstream for it  (specify we are creating a new branch and pushing the changes to the branch).
If we break something in the project, then we may use the history of commits to see which branch and commit specifically create the issue.  There is no straightforward way to make it linear, however...
We have a tool called `rebase` which will tear out the branch from somewhere and replay that history to someplace else.
Let's explore the following notation.
```bash
git rebase --onto main topicA topicB
```
We reapply all the deltas of the commits, without respect to the branches, onto the main. 
![[Pasted image 20251031130623.png]]
![[Pasted image 20251031130632.png]]

The rule of thumb is that it is better to still use:
```bash
git rebase --interactive --root
```
As, even if we are not changing anything, it is still good to see what we are dealing with. The haywire of merges from one to the other gets simplified into a linear list of hashes and comments. If we do not have any conflicts between the branches, then we do not have any conflicts during the rebasing.

If it is your own repository, or your own personal branch which you are working on, feel free to use `--force` to change history and whatever not. It is highly discouraged when working in teams, however, if one is working alone, he will not be interfering in anyone else's work with the force flag.

If you do not want your name or email to be associated with authorship of a commit anymore, or simply want to change the name or email across every single commit.
```bash
git commit --amend --no-edit --reset-author
```
This does reset the author and works as expected, but only works as a single commit.
However, we want to do this for every commit. How do we run it for every single commit?
For it, we have an available solution.
```bash
git rebase --interactive --root --exec="git commit --amend --no-edit --reset-author"
```
`--exec` Takes a script that runs after each commit.
What will happen is that we will be presented with the interactive rebase menu.
After each pick we have the exec command. It is pretty slow on very big repositories and may not always work as we expected, however, we successfully changed the author.

Though, there is a way better solution for that with amending, patching, and rewriting history. The best tool for it is `git filter-branch`. It is a potentially dangerous high-caliber tool, executing on every individual commit. 
![[Pasted image 20251031132055.png]]
There are also third party tools, namely, `git-filter-repo`. Installing it is straight forward, as it is a python package.
There is a very important warning for this. The script is installed at such and such path, which is not on PATH. We need to probably add this path there, to make the binary and script recognizable as a keyword in the terminal. For adding something into the path, we should add the path into your parsing script. You may type in whatever bash script that should be instantiated.
```bash
nvim ~/.bashrc
```
This is the config file in my machine. See what is the bash config file in yours.
Once in the `/.bashrc` file, we would want to add it to the path.
```bash
export PATH="My/Path/To/The/Script/Folder:$PATH"
```
Note that we are appending the last value of path to the end, to make sure we do not overwrite it. To check if it works, we may use the command `env`.
It is necessary to restart the shell in order for the PATH to be updated.
We may use `which` command to see the path of `git-filter-repo`.




Let's try solving another issue in our repository. For example, we do not want to have the binary files in the repository in most cases, and so, we want to delete them from all history.
```bash
git filter-branch --tree-filter 'rm -rf *.out' --prune-empty HEAD
```
We use force in the case the file isn't there, so that the rm command does not fail.

```bash
git filter-branch --index-filter 'git rm --cached --ignore-unmatch *.out' HEAD
```
The index implies that we are staying in the staging area and not going into the working directory, we will not be removing anything from the working directory.

In more complicated cases where the files we want to delete are distributed across directories, we should refer back to the `git-filter-repo` tool.
There is a nice catch to this, especially if we want to use manual pages, the actual name of the command git commit is git-commit. If it sees git [space] something, it translates it as git-something. 
```bash
git filter-repo --invert-paths --path-glob "**/*.out" --force 
```

Note that this will remove your origin because of the --force flag. Whenever we will try to push again, we will need to add the remote origin once again, and set a new upstream origin.

Two dashes in an execution of a script denote switches. Afterwards, the arguments.
There is a sly trick of using just `--` to denote the end of the switches, to ignore the following would-be switches. i.e. `nano -- --version` will create and open a file by the name of `--version` instead of execution the version switch.

<small> Irrelevant Mini-note: In AWS, there are no directories, they use the structure of a directory simply to be easier to read</small>
