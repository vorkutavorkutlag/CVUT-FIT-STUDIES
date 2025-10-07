This will be a continuation of last week's command line parsing presentation.

Shell splits the content of command-line into words. Default word separators are space, tab, new-line. Default word separators can be change by shell variables IFS.
This could be useful if you want to parse a file that is formatted in a way that is different from the way the shell usually parses files. Basically, you change the instructions to fit your work.
```sh
OLDIFS = " $IFS " # remember current value of IFS
IFS = " : " # set new value of IFS
# Read lines from the file / etc / passwd
while read name foo uid gid comment home shell
	do
		echo " name = $name uid = $uid "
	done < / etc / passwd
IFS = " $OLDIFS " # set previous value of IFS when done
```

To parse variables more accurately, it is possible and at times recommended to use the curly brackets {} surrounding it. For example, given the variable NAME:
```sh
echo $NAME1 # echos nothing, as NAME1 does not exist
echo ${NAME}1 # echos the value of NAME, followed by string "1"
```



The professor also went over a seemingly complex command-line that was discussed previously, that being:
```bash
finger | tail -n+2 | wc -l
```
finger returns a list of all users, where every line is a user, but it contains a header.
tail outputs the last part of files, but given that flag, it skips the first 2 lines.
`wc` prints the newline, word, byte count respectively, with the -l flag, prints number of lines.

Following, the file `/etc/passwd` was explored.
The "/etc/passwd" file in Linux is a critical system file that stores user account information, including usernames, user IDs, and group IDs. It is essential for managing user access and permissions on the system.
It appears as:
```
root:x:0:0:Super User:/root:/bin/bash
bin:x:1:1:bin:/bin:/usr/sbin/nologin
daemon:x:2:2:daemon:/sbin:/usr/sbin/nologin
adm:x:3:4:adm:/var/adm:/usr/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/usr/sbin/nologin
...
```

This is the file that the example shell script in the beginning of the note is referencing. Seeing it now, it is obvious why the separator had to be changed, as the separators of the different values are a colon `:` and not a newline `\n`. 
`while read` are the actual keywords, whereas, `name foo uid gid comment home shell` are the variable names we declared to parse the data. While it can keep parsing (read), the system is told to echo the name and `uid`. We feed the file into it as it iterates.
Afterwards, we return the IFS to its original form in-before the script was run.

#### Path-name Expansion
====================
###### Asterisk \*
Matching zero or more characters except the leading . (period) of a hidden file.
`ls -l *.txt *.c`
Returns the long-form content of the directory, filtered to only `txt` or `c` files.
###### Question mark ?
Matches exactly one character, except the leading . (period) of a hidden file.
`ls -l *.???`
Returns the long-form content of the directory, filtered to only files with an extension of length 3 characters (e.g. .txt). If there was only a single `?`, It would return only files with an extension of length 1 characters (e.g. .c)

###### Square brackets \[ \]
Matching one character in the set or in the range, except the leading . (period) of
a hidden file.
`ls -l file[0-9].html`
`ls -l file[367].html`-l
The former signifies a range from zero to nine, whereas the latter is a set of three numbers, three, six, and seven. It is **not** three hundred sixty seven
###### Square bracket inverse \[ \]
Matching one character not in the set or in the range, except the leading . (period)
of a hidden file.
`ls -l [^A-Z]*`

As a reminder, echo is a 'stupid' command and just prints the contents it receives as an zargument, whereas 'ls' is a smart command and pulls from environment information and changes its output accordingly; i.e. file permissions, terminal size, etc.
This does not mean one command is more useful than the other.
It means that there are different use-cases for the two commands.


#### Input-Output Redirection
=======================
File descriptor is an abstract indicator for accessing a file.
Every process has 3 standard POSIX file descriptors by default.
0 – standard command input (`stdin`)
1 – standard command output (`stdout`)
2 – standard command error output (`stderr`)
![[Pasted image 20251007103308.png]]

New process inherits file descriptors from his parent process by
default. User can redefine/redirect every file descriptor by special characters.
I/O redirection is evaluated from left to right.

###### `cmd < file`
Shell executes `cmd`, using file as the source of the standard input.
`wc -l < /etc/passwd`
###### `cmd > file`
Shell executes `cmd`, placing the `stdout` output in a file.
`date > out.txt`
`date > out.txt`

###### `cmd >> file`
Shell executes `cmd`, appends the `stdout` to the end of the file.
`date > out.txt`
`date >> out.txt`

###### `cmd << string`
Here-document, shell reads lines until the line beginning with the given
string, then all lines are sent to standard input.
```sh
cat > out.txt << END
> 1. line
> 2. line
> END
```
###### `cmd 2> file`
Shell executes `cmd`, placing the `stderr` output in the file.

###### `cmd >&n`
Shell executes `cmd`, placing the standard output in file defined by file
descriptor `n`.
`ls /etc/XYZ 2> err.txt >&2`

###### `cmd m>&n`
Shell executes `cmd`, placing the output defined by file descriptor `m` in
file defined by file descriptor `n`.
`ls /etc/XYZ > out.txt 2>&1`


To discard of unwanted output, you can use the 'black hole' of Unix systems, 
`/dev/null` data gets discarded definitely.

![[Pasted image 20251007104814.png]]

