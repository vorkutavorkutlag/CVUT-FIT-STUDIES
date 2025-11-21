[[COURSES/BIE-UOS/LECTURE 12 (TUTORIAL)|LECTURE 12 (TUTORIAL)]]
### REGEX

Regular expressions are a very powerful tool for modified text. The problem is, we are using similar metacharacters as we used with the shell, but sometime the meaning is different. So be careful with the context in which you are using any metacharacters.

For example, for the task to list the lines that contain the character 'a':
```bash
grep "a" input.txt
```
Then, how many lines contain 'a'?
```bash
grep -c "a" input.txt
```
How many lines contain 'a' or 'A'?
```bash
grep -Ec "[aA]" input.txt
grep -Ec "a|A" input.txt # Alternative 
```

Sometimes, it is necessary to add the flag `-E` to be able to interpret more regexes.

How many lines contain 'a' or 'A' at the beginning of a line?
```bash
grep -Ec "[aA]" input.txt
```
The `^` symbol has different meanings on context. Outside the square brackets, it refers to the start of the line. Inside the brackets, as in, `[^aA]` it would refer to everything that does not contain 'a' or 'A'.

How many lines contain 'a' or 'A' at the end of a line?
```bash
grep -Ec "[aA]$" input.txt
```

How many lines contain 'a' or 'b' or 'C' or '1' at the beginning of the line?
```bash
grep -Ec "^[abC1]" input.txt
```

How many lines contain 'a' or 'b' or 'c' at the beginning, and 's' or 't' at the end?
```bash
grep -Ec "^[abc].*[st]$" input.txt
```
In regular expressions, `.` means any characters. Then `*` defines it is repeated a number of times. Including zero.

How many lines contain 'a' or 'b' or 'c' at the beginning, or 's' or 't' at the end?
```bash
grep -Ec "^[abc]|[st]$" input.txt
```
The pipe, outside the brackets, means that it is either the first expression or the second expression.

How many lines contain at least 3 times the character 'e'?
```bash
grep -Ec "e.*e.*e" input.txt
```

How many lines contain a *word* starting with 'a' or 'b'?
```bash
grep -Ec "\<[ab]" input.txt
```
In regex, `\<` denotes the beginning of the word, where as `\>` denotes the end of a word.
By POSIX standard, it separates at space and punctuation characters.

List the lines that contain a word starting with 'a' or 'b' and end with a vowel `aeiouy`
The intuitive but wrong solution:
```bash
grep -E "\<[ab].*[aeiouy]\>"
```
Here, `.` can be any character, including the separator. It is necessary to take into account all separators.
```bash
grep -E "\<[ab][[:alnum:]]*[aeiouy]\>"
grep -E "\<[ab][a-zA-Z0-9]*[aeiouy]\>" # Alternative
grep -E "\<[ab][^[:punct:]]*[aeiouy]\>" # Alternative
```

From the file "words", list the lines that have the same leading and trailing character.
```bash
grep -E '^(.).*\1$' words
```
...With only 5 letters (like trident):
```bash
grep -E '^(.).*\1$' words | grep -E '^[[:alnum:]]{5}$'
```

From the file "b.txt", list the lines that contain at least two of the same word
```bash
	grep -E '\<([[:alnum:]]+)\>.*\<\1\>' b.txt
```

There was some random text and we have to display all lines with a word which contains ten letters (upper case, lower case, digits)
```bash
grep -E '[a-zA-Z0-9]{10}' text.txt
grep -E '[[:alnum:]]{10}' text.txt
```

One instance of a character in a line
```bash
grep -E '' input.txt
```

All lines that contain two words that contain character 'e':
```bash
grep -E '\<e[[:alnum:]]*\>.*\<e[[:alnum:]]*\>' input.txt
```
