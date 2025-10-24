## Conflict Resolution


Conflicts occur when several developers try to introduce changes into a repository that clash with one another. i.e., two independent branches that work on the same bytes in a project. When they try to merge the branches, git does not know how to resolve the conflict, as in, who to give the priority to, and whose changes to discard. For that, we have to specifically tell git in what manner to approach the conflict.

First of all, there is the option of stashing your own changes to another place using
```bash
git stash list --patch 
```
The stash is a stack-like data structure, following the first in last out doctrine. 

Afterward, using `git status` you will be able to see that there are no changes to be made. That means that you will be able to do `git switch` in order to switch the repository. 

Right after, to bring the changes back
```bash
git stash pop
```
Will pop the last stashed change and put it in your working directory.

To create a new branch without using branch, we may use `git checkout`.
`git checkout` takes the content of the repository and unpacks it to the working directory. If you want to checkout a branch that is not existent, it will create the branch
```bash
git checkout -b name
```
If we want to copy from master:
```bash
git checkout -b name master
```


Making changes, and then switching to the master branch, later on, you may use
```bash
git merge name
```
If it fails, it should give you the error message:
CONFLICT (content): Merge conflicts in ...

Merge conflict, no matter how professional a team is, are inevitable, and it is important to know how to resolve them. When encountering a merge conflict you usually have to open the file(s) that is causing the merge conflict. 
At that point, git will have added additional information showing where pointers to branches are. You should edit the file to coincide with the goal, and delete git's addition (long lines with names of branch pointers and control lines). Once you have done that,

Then,
```bash
git merge --continue
```
After that, we may use `git ll` once more to see how it the graph looks like.


To rest to a commit before this commit
```bash
git reset --soft HEAD^
```
Where the `^` symbolizes to one commit before the one specified (`HEAD`).

As discussed in the last lecture, to manually change the deltas git will be committing,
```bash
git add -p
```
git add patch.


```bash
git reflog
```
Can be use to try and find orphaned commits that are still kept for 30 days after they are severed.


```bash
git cherrypick [hash]
```
allows you to select specific commits from one branch and apply them to your current branch, effectively copying changes without merging the entire branch. This is useful for backporting bug fixes or applying individual changes from one branch to another in order to gradually resolve the conflict.
