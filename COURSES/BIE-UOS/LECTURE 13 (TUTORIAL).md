[[COURSES/BIE-UOS/LECTURE 14|LECTURE 14]]
# Shell Scripting

Create a shell script that prints the number of lines in /`etc/passwd`.

```bash
#! /bin/bash
wc -l < /etc/passwd
```
We define the shebang for the shell, putting the path to the shell.
In the real world, `#! /usr/bin/env bash` is more versatile.
Then, we redirect the input to not print the name of the file. If we do not want to redirect, we can pipe it into cut such as:
```bash
wc -l /etc/passwd | cut -d' ' -f1
```
Then, in the terminal, we check the file's permissions using `ls -l script.sh`.
We see that we have reading and writing, but no execution permissions.
One solution is writing the path to the shell, and then giving our script as an argument, or redirection input, writing `bash script.sh` or `bash < script.sh`
However, to run our shell directly with `./script.sh`, we must give it permissions.
Using `chmod u+x script.sh` We add execution (x) permission for the user (u) to the file.


Create a shell script that:
- Prints the number of lines of the file, that is defined by the first argument.
- Checks the argument if it is correct. No argument means no readable file, print help message.

```bash
#! /usr/bin/env bash


if (( $# != 1 ));
	then printf "Usage: %s filename" $0 1>&2
	exit 1
fi

LC=$(wc -l < $1)
printf "File %s has %s lines\n" $1 $LC
```
`$n` represents the nth argument for our shell. We can grab the name of the script with `$0`, and then the first argument with `$1`, second argument with `$2`, and so on.
First, we need to check if we were given an argument to begin with.
We can see the number of arguments we were given with `$#`.
We check the arithmetic, see if the number of arguments is equal to one.
Some basic bash condition syntax later, we return early if we see a problem.
Additionally, we will redirect the error into `stderr` using `1>&2`
Otherwise, we will run the command.

Alternatively, we may replace the condition in if with a test.
```bash
...
if [-f "$1" -a -r "$1"]
...
```
Translating roughly as: if `$1` is a regular file, and, if `$1` is readable to us.

Now, to rewrite the script in a way that gets an arbitrary among of arguments.

```bash
#! /usr/bin/env bash

if (( $# == 0 ));
	then printf "Usage: %s [ filename1 filename2 ... ]" $0 1>&2
	exit 1
fi

for ARG
	do
		if [[ -f "$ARG" -a -r "$ARG"]];
			then printf "Not a readable file: %s" $ARG 1>&2
			exit 1
		fi
		
		LC=$(wc -l < $1)
		printf "File %s has %s lines\n" $1 $LC
	done
```

Create a shell script that:
- Calculates the sum of script arguments (integers)
- Checks these arguments if they are correct (no argument or no integers)
```bash
#! /usr/bin/env bash

if (( $# == 0 ));
	then printf "Usage: %s [ int1 int2 ... ]" $0 1>&2
	exit 1
fi

SUM=0
for ARG
	do
		echo $ARG | grep -E '^-{0,1}[0-9]+$' > /dev/null 2>&1
		if (( $? != 0))
			then printf "Not an integer"
			exit 1
		fi
		((SUM += $ARG))
	done

printf "The sum is: %s" $SUM
```
When grep does not find it, it does not return 0. 

Though, in a shell script, we can combine the grep and if condition into a single line.
That is because it returns an exit code, and by checking `#?`, we are basically checking it.
```bash
...
if echo $ARG | grep -vE '^-{0,1}[[:digit:]]+$' > /dev/null 2>&1;
	then
...
```
Note that we have to reverse it in this case, using the `-v` flag in grep.

Next test we will be using if, for, while, etc.
