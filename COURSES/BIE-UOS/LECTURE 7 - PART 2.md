
## UNIX FILE-SYSTEM
As opposed to other operating system archetypes such as that of Windows, the Unix-like operating systems share a single root, that being `/`
![[Pasted image 20251014080512.png]]
The data is a single structure and can be traversed using commands such as `cd`, to switch the current directory, as well as `ls` with its flags.
Using the command `df` returns the a report of the file system space usage. i.e., how much weight in bytes (/mb/gb/etc.) the system has mounted, and how it is distributed.
To mount a filesystem, you may use the `mount` command. Without any arguments, it will display information about the filesystem.

Some important directories.
![[Pasted image 20251014081141.png]]

#### File
In Unix, the term file is much more general than in other OS.
The file can represent a regular file, a directory, a special file, a symbolic link, etc.
The name's maximal length is file system dependent.
Code depends on implementation (ASCII, UTF8, etc.)
Any characters are allowed except `/`
Hidden files are denoted by those beginning with a dot, and not substituted by symbols * and ?. Additionally, command `ls` doesn't list them by default (unless with `-a` flag)
File names dot (`.`) and double dot (`..`) are reserved to working directory and parent directory respectively.

![[Pasted image 20251014084645.png]]


With a Hard Link, attributes and data of a single fine are accessible through several filenames.
It can be created only within the physical file system. It cannot point to neither a directory nor a non-existing file. After the creation of a hard link, it is impossible to distinguish between the original and new file name. As for removing, i-node and data are removed when the last name are removed.

`ln original file name new file name`

![[Pasted image 20251014084926.png]]

With a Soft Link, it contains original file name in its data block or in its i-node.
It is possible to create a soft link to a directory, non-existing file and between different physical systems. Some operations are made directly with soft link (rm), another ones
with the file on which the soft link points (vi)

`ln -s original file name new file name`

![[Pasted image 20251014085110.png]]
![[Pasted image 20251014085339.png]]


Note: was absent in this part of the lecture, refer to:
https://courses.fit.cvut.cz/BIE-UOS/lectures/bie-uos-p03-fs-01.pdf 
Or the lecture's recording for more specific information.

The basic commands for work in directories:
`cd`: change working directory
`ls`: list contents of directory
`mkdir`: make new directory
`rm`: remove directory (-r removes including its contents)
`cp -r dir1 dir2`: if dir2 doesn't exist it creates a copy of dir1 by the name dir2
				otherwise, creates copy of dir1 inside dir2
`mv dir dir2`: if dir2 doesn't exist, rename dir1 to dir2
				otherwise, moves dir1 to dir2 (dir2/dir1)

Basic commands for work with files:
`cp f1 f2 dir`: copies all listed files to the directory
`cp f1 f2`: if f2 doesn't exist, copy f1 to file f2
			otherwise, overwrite file f2 by f1.
`mv f1 f2`: move/rename f1 to f2
`rm f1`: remove f1

`stat f1`: display attributes of file f1
`file f1`: determine type of file f1.
`cat f1 f2`: concatenate and display contents of two files
`less f1`: browse or page through text contents of f1
`od [-c/-x] f1`: Octal dump (print contents of file f1)
`strings f1`: display printable strings in file f1.