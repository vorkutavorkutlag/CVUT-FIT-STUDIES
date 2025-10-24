[[COURSES/BIE-GIT/LECTURE 3|LECTURE 3]]
## Git Installation & Basic Commands
=======================================

Using the apt package manager, you may install most packages if you add root permissions to the command line.
```bash
sudo apt install git
```

Other distributions may have different package managers, i.e. `dnf` for fedora.
You may use

```bash
git --version
```
to see what git version has been installed (if any).
If it prints a valid version, it has been installed successfully.
 
 To initialize a repository (thus creating a .git folder):
```bash
git init
```
After initializing a REPO (repository) in your WD (working directory), you may execute other git functions in the directory.

For that, it is important to understand the Staging area / Index. 
WD    ->      SA/I    ->   REPO
    ADD         COMMIT
The SA/I is needed for many situations, the most prominent of which is a situation where you only want to add *some* of the changes you have made in your working directory over to your repository. For example, we may use:
```bash
git add [filename/directory]
```
This will add a file or directory to the current commit change (SA/I). If it returns nothing, it most likely succeeded.
To see how our current SA/I looks like, it is recommended to use:
```bash
git status
```
It will show us all the changes that would be made were we to commit them to the repository. Also, highlights which changes we made that are not committed.

The next step in the process is committing the change. A necessary requirement for committing, is editing your git configuration's author information. This has to be done only once per initialization of git (specifically of git as a whole, not a necessarily repository)
```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
According to git, it doesn't have to match anything in particular, as git does not compare or check these values. Still, it is necessary to have them set. 
For this course, it has to be set to your name and university email.

```bash
git commit
```

Note: The ideal commit changes one thing at a time so that the versioning could be done most efficiently. Say, you want to remove a certain change, but keep the rest, it will be increasingly more complicated and difficult if you commit several different types of changes in the same time.

After this command, it will launch an editor within the terminal, usually using vim, where you will have to write a message for the commit.
There are plethora of ethics for writing proper commits, but aren't too relevant to BIE-GIT. 
The first line of the commit message is usually the subject. The lines afterwards are the description. Exiting the editor without a commit message will abort the commit. 
The professor recommends using the editor, as it gives you a moment to comprehend what you have changed and write a proper commit message.

Basics for vim:
`I`= to enter insert mode and be able to write.
`CTRL+C`= leave mode and enter command mode. Unable to write on text, but able to execute commands.
`:w` = Write. Save the changes.
`:q` = Quit the editor.
To change the editor, you may edit the config.
```bash
git config core.editor EDITOR
```


Alternatively, it is possible to issue a message in an easier, shorter way.
```bash
git commit -m "Hi! I changed this and that."
```

```bash
git commit --amend
```
 Allows you to modify the most recent commit, enabling you to change the commit message or add new changes to it. This command effectively creates a new commit that replaces the old one, so be cautious if the commit has already been pushed to a shared repository.

With a commit message, git will be able to process the commit.
Afterwards, git status will show that you have nothing to commit on the current branch.
To view your previous history of commits, it is possible to use:
```bash
git log
```
It gives a compact but informative overview of the commits, showing the HEAD pointing to the branch you committed it to, and master in itself is pointing to an object in the git database.
Side note:
```bash
git log --oneline ---graph --all
```
Most git commands have plenty of flags which you can find with the `man` command (bash manual), which may alter the output or the format of the command.

```bash
git log -stat
```
Shows the statistics. Useful for catching files/dirs that we accidentally added.


It is possible to use `diff` to see the difference between the SA/I and the WD.
```bash
git diff
```
It will compare between the current uncommitted changes and the last commit/pull in the staging area. To add the changes to the SA/I, simply `git add` once again.
Additionally, even if you add the changes, you may still see what you have changed flag:
```bash
git diff --cached
```
Likewise, this will be useful in collaboration with others:
```bash
git diff --cached --word-diff
```


It is possible to create aliases for git, as in, sort of shortcuts for longer commands.
It is not necessary, but recommended for comfort and debugging
```bash
git config --global alias.ll "log --oneline --graph --all"
```
Through this, running the command `git ll` with be equivalent to running the command:
```bash
git log --oneline --graph --all
```



To quickly add all the files in the working directory , it is possible to use shortcuts. i.e.:
```bash
git add .
```
It will add all the files and sub-directories of the directory you are working in.
Alternatively, using:
```bash
git add *
```
The difference being `add *` means add all files in the current directory, except for files whose name begin with a dot. This is your shell functionality and **Git** only ever receives a list of files.

`add .` has no special meaning in your shell, and thus **Git** **adds** the entire directory recursively, which is almost the same, but including files whose names begin with a dot.


As git works on branches, it is important to keep in mind which branch we are working on. Master and Main branches may be used interchangeably in the course, and their definition is the central branch of the repository.
```bash
git branch
```
Returns the list of available branches. Branch marked with `*` is the one you are working on.
In order to get more help on branches, you may use:
```bash
git branch -h
```


To create a new branch, you may use:
```bash
git branch newbranch
```
Alternatively, adding an additional argument, (hash) a pointer to a point in the repositories history (found through git ll), it will branch it off from that point.
```bash
git branch newbranch aaacbb3
```
<small> It is repository specific, and this ID is just an example </small>


To switch from one branch to another, you may use:
```bash
git checkout branchname
```
At the same time, you may use:
```bash
git switch branchname
```
Which has the neat trick of:
```bash
git switch -
```
That translates as "switch to the branch I was at previously".

After a repository has more than one branch, `git ll` will print a bottom-up graph that shows the main branch in the middle and other branches splitting from it.

To merge the branches, it is possible to use:
```bash
git merge branchname
```
Which, after writing a merge message, will merge that branch with the main/master branch.
If there are any conflicts, you will need to resolve them in-before you merge, as git won't automatically take one change over another. Printing `git ll` again, we will visualize the merging of the branches, as the stray branch will enter the central main/master one. 

In case you made commits that you are unsatisfied with, you may reset the SA/I and WD to the REPO's current formulation.
```bash
git reset HEAD
```
Will move the HEAD to the previous commit. Alternatively, it is possible to provide a commit hash to tell it where to go to.
```bash
git reset c6b0aa9
```

To make sure you never add the same file/directory which you do not want to add ever again, it is recommended to create a text file called `.gitignore` , in which you will write all the files (or all the regular expressions) that you instruct git to ignore from now on. For example,
```
secrets.txt
*.png
```
Will ignore the file `secrets.txt`, and all the files that end in `.png`.
It also automatically ignores the `.gitignore` file, unless you specifically added it (can used the -f force flag to force it to add it if it ever objects.)
It is a good practice to add and keep updating `.gitignore` in projects, such that secrets or unwanted files do not leak out on accident.  

```bash
git remote add origin <URL>
```
Now, to link it to a repository and to upload the changes to the git databases.


```bash
git push --set-upstream origin-master
```
Set the upstream (where you will be pushing into) of the repository. 

These two commands need to be done only once.

Given you have an ssh key and linked it to your github account, you may use:
```bash
git push
```
This will push the commit into the repository on the database, and others (including you) will be able to access it remotely.