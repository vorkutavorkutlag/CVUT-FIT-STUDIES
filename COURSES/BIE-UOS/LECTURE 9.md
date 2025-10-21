## Filters
Filter is a simple program that gets its data from its standard input (the main input stream) and writes its result to its standard output (the main output stream).
Filters include `head, tail, wc, cut, tr`, etc.
Filters are often used as elements of pipelines.
Not every command in Unix is a filter! For `rm`, which is not a filter, you may not do:
`ls *.txt | rm`. The correct syntax would be:
`rm *.txt`.

It is best to use Unix filters instead of C as it is not a proprietary solution, anyone can modify the solution, and there exists platform compatibility.

`tee [options] [files]`
The filter reads lines from standard input and writes them to standard output and files.
Options: 
-a appends output to the files
Examples:
How many items (file, directories, etc) are in the directory /etc?
Save list of items to the file `items.txt`.
Print the number of items to the standard output
`ls /etc | tee items.txt | wc -l`

Note that it is different from output redirection, which only forwards the output to one direction, tee, as the name implies (T), will split it in more than one direction.
`ls /etc > items.txt | wc -l` will not work. If you are persistent on using I/O redirection operands, the problem will be solved in two steps.
`ls /etc > items.txt; wc -l < items.txt`

`nl [options] [files]`
The filter numbers lines of the standard input/files and prints them to the standard output.
Options:
	`-s'sep'`... sep is the character(s) used in separating the line number.
`-bp'pattern'`... only lines containing pattern will be numbered.
Examples:
	Default lining number:
	`ls -l /etc | nl`
	New separator between numbers and original line.
	`ls -l /etc | nl -s') '`
	Only lines with pattern will be numbered:
	`ls -l /etc | nl -bp'^-'`

`wc [options] [files]`
The filter prints a count of lines, words and characters of standard input/files to the standard output.

Options:
	`-c` count bytes
	`-w` count words
	`-l` count lines
Examples:
	How many items are in the working directory?
	`ls -a | wc -l`.

`tr [options] set1 set2`
The filter copies the standard input to the standard output with substitution or deletion of selected characters. The set1 and set2 operands control translations that occur while copying characters
Options:
	`-c` use the complement of set1 (can be used to 'protect' ranges instead of replacing)
	`-d` delete all occurrences of characters present in set1
	`-s` replace all instances of repeated characters by single character

Meta Characters
	Ranges:
		`'M-N'` all the characters from M through N
	Classes:
		`[:CLASS:]` expands to all of the characters in the class CLASS
	Repeated Characters:
		`[C*N]` in set2 expands to N copies of character C
		`[C*]`expands to as many copies of C as are needed to make set2
			as long as set1

Examples:
	Replace the characters: a → X, b → Y, and c → Z, in the output of the command ls -l /
	`ls -l / | tr 'abc' 'XYZ'`
	Replace all lower case with upper case
	`ls -l / | tr 'a-z' 'A-Z'`

`head [options] [files]`
The filter prints first 10 lines of standard input/files to the standard output.
Options:
	`-k` copies the first k lines from standard input to standard output.
	`-n-k` copies all lines except the last k lines from standard input to standard output.
Examples:
	List names of the five largest files from the working directory:
	`ls -S | head -5`
	List names of the three files from the working directory whose content
	has been last modified:
	`ls -t | head -3`

`tail [options] [file]`
The filter prints the last lines of the standard input/file to the standard output
Options:
	`-k` begins printing at the $k_{th}$ item from end of file
	`+k` or `-n+k` begins printing at the $k_{th}$ item from beginning of file
	`-f` doesn't quit at end of file
Examples:
	List names of the five smallest files from the working directory:
	`ls -S | tail -5`
	List the five largest files from the working directory including details:
	`ls - lS | tail -n +2 | head -5`
	Execute the following commands in two different terminals:
	
	`date > / tmp / f ; tail -f / tmp / f`
	`for (( i =0; i <5; i ++)); do sleep 2; date >> / tmp / f ; done`
	
	This will keep running, as a result of the -f flag making it not end.

`cut [options] [file]`
The filter cuts out selected fields of each line of the standard input/file and prints them to the standard output.

Options:
	`-c list` specifies characters
	`-d delim` defines delimiter (-f option only)
	`-f list` specifies fields separated by delimiters.

Examples:
	For each file in your working directory, list its access rights and name
	`ls -l | cut -c2-10,54- # Attribute dependent solution`
	`ls -l | tr -s ’ ’ | cut -d ’ ’ -f1 ,9 | cut -c2 -`
	
	For each user account on the server fray2.fit.cvut.cz, print the account name (the first item) and user information (the fifth item).
	`ssh trdlicka@fray2 . fit . cvut . cz \`
	`’ getent passwd | cut -d ":" -f1 ,5 ’`

`paste [options] [files]`
The utility merges corresponding or subsequent lines of files and print them to the standard output.
Options:
	`-d[list]` each character in list is an element specifying a delimiter character.
	`-s ` concatenate all of the lines of each separate input file in command line order.
Examples:
Save the name, uid and shell of users who have an account on this server to the files /tmp/name, /tmp/uid and /tmp/shell, respectively.
```bash
getent passwd | cut -d " : " - f1 > / tmp / name . txt
getent passwd | cut -d " : " - f3 > / tmp / uid . txt
getent passwd | cut -d " : " - f7 > / tmp / shell . txt
```