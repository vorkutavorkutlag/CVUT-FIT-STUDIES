
// This is very messy and should just be used to skim through commands we learned

The data in UNIX is organized as the tree of directories. At the very top is the root directory, denoted by `/`. As opposed to Windows' File Explorer, which contains drives, and those drives contain their respective directories.
The shell is very strict on syntax. For example, the top line will result in an error, whereas the bottom one won't.
```
A = abc
A=abc
```

`man`: manual guide, shows how a command functions 
argument: valid unix command
example: `man ls`

`cd`: change directory.
argument: valid path
example `cd /etc`

`ls`: returns contents of the working directory
flags: `-l` (long) more information. Directory/File, permissions, date created/modified, size, etc.
argument: none
example: `ls`

`echo`: given data, it 'repeats' it in the standard output
argument: the data the user wishes the shell to repeat
`$` will read the data given to it instead of simply printing the exact string.
example:
```
A=abc
echo A
A
echo $A
abc
```

`set`: allows to enable flags in bash scripts and influence the environment

`export`: marks an environment variable to be exported to child-processes, so that the child inherits them.
example:
```
export TZ=Asia/Japan
echo $TZ
```

```
user@pc:~$ export PS1-"AAA"
AAA: ....
```
[PS1 is the Prompt String One environment variable, being the string in-before the command prompt in the shell. Using `export`, it is editable.]

`gnome-terminal &` will create another ssh terminal as a child of the original one, though it will have its own local environment, even if it inherits the local variables made up to that point.

`pwd`: Print Working Directory - prints the directory you are in
- There is also a variable called $PWD, which, if echoed, gives the same output as `pwd`.


`mkdir`: make directory
argument: path to the would-be directory you want to make
example: `mkdir uos1`

`df`: shows the filesystem table. size, used, avail, use%, mounting location
flag: `-h`: converts sizes to M, GB, etc.

`uname`: prints information about OS 
flag: `-a` prints further information (ie, distribution, version, etc.)

`lscpu`: prints information about the CPU

###### `|`: Pipe
Feeds the output of the previous command slice as an argument to the command slice that follows it.

`lscpu | less`: will display the contents of lscpu in a terminal, instead of printing it.


using asteriks (\*\*) you may find similar files/directories.
```
~$ echo /etc/*release*
/etc/os-release
```
the name `os-release` contains the string `release`, and so, using asteriks, it is possible to find.

`cat`: returns the contents of the file in text

