[[COURSES/BIE-UOS/LECTURE 9|LECTURE 9]]
Command line parsing exercises.  IO/expressions
For example, 
to find all the files ending with q: `ls *q`
to find all the files starting with q: `ls q*`
to find all the files that do not start with q: `ls [^q]*`

In the test you will need to find files with several regular expressions. You can chain them, for example: `ls -1 *.c .*.c` Shows all hidden and unhidden c files. It is made up of two different regular expressions as arguments.

Note: `ls -1` lists 1 file per line.

