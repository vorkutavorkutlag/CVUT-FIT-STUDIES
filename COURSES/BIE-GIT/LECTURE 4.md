```bash
git add -p
```
To add changes separately.

Given a repository with a main branch on which you try to integrate everything, it is important to understand the difference between git rebase and git reset.
Git reset is used to move the current branch to a specific commit, effectively altering the commit history, while git rebase is used to reapply commits from one branch onto another, maintaining a linear history. Reset can be more destructive, as it can remove commits, whereas rebase is generally safer for incorporating changes without losing history.
Because I didn't pay attention to this lecture, consult with "git explained with cats".

Objects that are made up of the same binary are resembled by the same hash through a deterministic function, and such will be stored in the same place in the database if it were recreated. Only the content of the file is what matters, its name is not respected when calculating the hash.

To merge changes in the history, or remove a file in the history, or making other changes, we face the issue of fighting against the git architecture. In that case, you may use rebase, yet rebase will work on the commits automatically, picking the commits that are different in the branch and automatically move them somewhere.
However, if we want to do it interactively, we may use `git rebase --interactive` .
It is followed by arguments being the hashes or defined variable.  i.e.
```bash
git rebase --interactive origin/master
```
The interactive mode of rebase is a rather complex editor that you will need to read the manual or watch a tutorial on. I have no hope of trying to explain it in this lecture.