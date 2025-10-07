[[COURSES/BIE-UOS/LECTURE 4|LECTURE 4]]
# COMMAND-LINE PARSING
# META-CHARACTERS
# COMMAND EXECUTIONS
# SHELL VARIABLES


Shell parses expressions in its specific and very not lenient ways. Spaces and tabs are known to break the formatting of the parse, as they can be used as separators for expressions and multiple arguments. For example, you may declare two variables on the same line.
```bash
a=Hello b=World!
echo $a $b
// prints "Hello World!"
```

In cases that we want to use characters that otherwise would break our formatting, we have to employ meta characters (such as quotation marks).
```bash
A = "Hello World!"
echo $A
// prints "Hello World!"
```

This can be used for more complex expressions.
```bash
B="Num of logged-in users: $(finger | tail -n+2 | wc -l)"
echo $B
```

finger returns information on the logged in users, which we 'feed' into tail, that takes the last part of everything given to it, which we then feed into wc, which, with the flag we chose, counts the number of new lines.

Shell repeatedly performs command-line reading, command-line parsing, variable setting and execution. During the command-line parsing, the meta-characters are interpreted or replaced by the shell in the exact order.
The command line parsing order is as follows:
1. Quoting: `\, '...', "..."`
2. Comments: `#`.
3. Command line splitting: `|, ;, &, &&, ||`.
4. Special characters: `{...}, ~, ‘...‘, $, $(...), $((...))`.
5. Word splitting: space, tab, new-line.
6. Pathname expansion: `*, ?, [...], [!...], [^...]`.
7. I/O redirection: `<, >, >>, <<END`.
8. Options and arguments setting.

###### Quoting
It is possible to turn off the special meaning of letters by using other characters. The backslash `\`, turns off the reading symbol `$`.
For example, `\$HOME = $HOME` will create a new variable by then name of "$HOME" that is equal to the expression $HOME, which is the path to the home directory of the system.
Apostrophes turn off the special meaning of all letters between them (except apostrophe). For example, `'$ \ * < > | & ; ... '`
Double quotes turn off the special meanings of all characters except: `\ $var $(cmd) $((exp)) '...'`.

```bash
echo "\$HOME is $HOME" # variable substitution
echo "Today is $(date + %A)" #command substitution
echo "TOday is 'date + %A'"
echo "1 + 1 = $((1+1))" #arithmetic expansion
```

With the user load example:
```bash
Load=$(finger | tail -n+2 | wc -l)
echo $Load
```


An important note about the parsing of the shell is the fact that it does not 'update' old variables even if they 'depend' on variables you've changed.
```bash
N1=2
N2=4
SUM=$((N1+N2))
echo $SUM # prints 6
N2=20
echo $SUM #still prints 6!
```

There exists synonymity of some expressions in bash. For example, `$(cmd)` can be substituted with \`cmd\` (cmd surrounded by back-apostrophes). Still, it is suggested that you use the new syntax (with the dollar sign).

###### Comment
The comment is defined by the hash symbol. If it is at the beginning of the line, it has a different meaning. For example, `#!` means that what follows is the path to the interpreter of the bash - this is why most shell scripts start with
```bash
#! /bin/bash
```
To be given the functionality of a comment, it has to be 'in the beginning of the word'. Proper comments include:
```bash
# Example of a shell script
#This works as a comment as well
uname -s # OS
uname -m #hardware architecture
echo Hello world#this is not a comment
```
The last line is flawed.


###### Command-line splitting
The most simple use of command line splitting is the passing of arguments, flags and parameters to commands. For example, `cd $PATH`. The space bar is used as a splitting character, and so the system interprets it as passing the expression of $PATH as an argument to the command.

One of the most common operations in the bash command splitting realm is the pipe function ( `|` ). It takes the output of the previous expression and executes the following expression with the previous output as a new argument. It can be a bit tricky, as some commands such as `ls` are "smart", and take into account whether it is being displayed in the terminal or piped. Even if it is displayed in the terminal, the number of lines it outputs is dependent on the size of the terminal (the smaller it is, the more lines it will have to use to compensate). Another important aspect is what the expressions return. usually it's some sort of exit code, For example, there is a clear distinction:
```bash
ls | wc -l # prints 2
echo ls | wc -l # prints 1

# We expect it to return 1, as ls returns a line of all the files and firs in cwd
```


The semicolon can be used to create new commands in the same line. It is equivalent to pressing enter and beginning to write a new line of code, except, now, it will be executed right after the other. For example:
```bash
date ; sleep 2 ; date # prints the date, then the same date but 2 seconds in the future
```
The ampersand (&) in Bash is used to run commands asynchronously in the background, allowing you to continue using the terminal without waiting for the command to finish. This means the command will execute independently while you can run other commands simultaneously. For example:
```bash
sleep 5 &
```
Will create a thread that sleeps for 5 seconds, and next time you do a prompt in the shell, and the thread has finished its task, it will say it is done and terminate itself (join back to the main terminal).

Another example is:
```bash
ls; date; #prints the contents of the dir, then the date
ls & date & # prints the date, and then the contents of the dir, because the command is asynchronous and date is computated slightly faster than ls, and so it's the first to 'win the race'.
```

For the next expression it is important to understand the exit/return codes of expressions. In the following case it is a number passed from a child process to a parent process when it has finished executing. `0` is Success, anything else (1..255) is Error.
`cmd1 && cmd2`: cmd2 is executed if and only if cmd1 returns an exit status of zero.
`cmd1 || cmd2`: cmd2 is executed if and only if cmd1 returns a non-zero exit status.

###### Special Characters
![[Pasted image 20251007093113.png]]
![[Pasted image 20251007093131.png]]


