Repeating previous topic of scripting briefly. Including the default for `for `loops being `$@`, that being the list of arguments.
Then, testing whether an argument is an executable file.
The task itself was to find how many arguments from the given arguments were executable arguments.
The solution is as follows.
```bash
#! /bin/bash
SUM=0

for ARG	do
	if [-f "$ARG" -a -x "$ARG"] ; then
		((SUM++))
	fi
done

echo $SUM

```

Anyway, we will be discussing permissions and find command today.
Most of the time, we will be using `chmod -R` to recursively change the permission of a directory. The symbolic mod is best, as it allows you to change permissions based on group.
For the owner, we can do `u=rwx` for some group, `g=rx`, and for anyone else, `o=r`
If we want to calculate the permission, we may calculate the total sum of the permissions, as it will be unique.
Reading = 4, Writing = 2, Executing =1
The previous values of the permission are lost.

If we want to set up the same permission for all the files under a directory,
```bash
chmod -R u=rx,go= /tmp/uos
```
User has reading, executing, group & other have nothing
Doing `find dir -ls` will list the structure and permissions.
Otherwise, if we use the `-ld` flag, we see the permissions of the directory itself.

Wee bit of theory:
The read permissions imply we can read the datablock, but the execution permission  allow us to access the i- node

The minimum permissions needed for executing a command...

