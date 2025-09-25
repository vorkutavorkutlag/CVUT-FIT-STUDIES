
Opening Debian on the school computer, and trying out some basic commands, such as `hostname`, `whoami`, and `echo`. You did not necessarily need Linux on your laptop.


At the very top is the root, the parent of all the the other directories. Its children include `etc`, the directory for configurations, `temp`, the directory for temporary contents, and `home`.
`home` houses the directories representing each one of the operating system's users. If there is only one user, there will only be one directory. The children of that directory are the home directory of that user, that can be represented as `$HOME`.
From that we can observe different ways to traverse to the home directory:
```
cd $HOME
cd ~
cd /home/{username}/linux-home

// dependant on cwd (current working directory):
cd ../home/{username}/linux-home
```
-  `..` goes a directory "up" in the directory tree. As in, leaves the current the current directory and goes to its parent.

Playing with these paths is also possible in other commands, for example, in `mkdir`. If you're at the root directory as a normal user, you cannot create a directory there. However, you could....:
`mkdir ~/{directory}`
Wherein `~` represents the user home directory, and {directory} represents the directory (or path to the directory) that we wish to create.
- This can also be achieved by `mkdir $HOME/{directory}`, and other methods.

##### Filesystem Server
==============
The classroom uses a filesystem server, wherein all the computers share a storage. The directories from the server are mounted on the computer you are using each time you log in through your username and password. Making modifications, you may see them again in a different computer if you log in with the same user. (CTU username and CTU password).
The root directory is individual per every machine, but the home directory, which is also saved in the filesystem server, may change per every individual user that logs in.


##### SSH (Secure Shell Protocol)
=====================
Generating an SSH key using `ssh-keygen -o` in the terminal and following the instructions, you may log into https://gitlab.fit.cvut.cz/-/user_settings/ssh_keys/28400 and upload your public ssh key. After that, in the terminal, you may use the command:
`ssh {CTUUSERNAME}@fray1.fit.cvut.cz`, and agree to the fingerprint of the host. If the ssh key is present in your `.ssh` folder (which it should be after generation), and you have uploaded it correctly, you should be able to log right in.