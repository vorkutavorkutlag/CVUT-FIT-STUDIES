## Fixing mistakes in an organized way
#### And others useful information

You may regenerate ssh keys and reintroduce them into your git profile whenever you desire. Simply follow the same process as the first time generating an ssh key.

What happens when you write git clone?
If there exists such a repository that has commits in the git database, then it is considered a remote repository - a repository that is saved somewhere outside of our local machine. 
Secure Shell, unlike FTP (File Transfer Protocol), is not a protocol, and in git's case, is a very limited amount of access between our local machine and the remote. 

`git clone` has several steps. First we initialize an empty repository using `git init`, it creates a `.git` folder with some configuration, and then we are ready to clone. The next command ran is, `git fetch` transfers files from the remote origin, copying the repository to your local, empty repository. All of the blocks, tree objects, commits etc. will be transferred as a compressed pack file to your machine, after which the process unpacks them.


Something something, worktree, stash...

To change the file across history we can remove the file at all through the entire repository with --invert paths. And then rebase interactive to the point where we want to introduce it, or create a fix-up.
