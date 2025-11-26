
## sed & awk


2. From file f1, print only lines 3, 5-10, 15 up to the last line.
```bash
sed -n '3p;5,10p;15,$p' f1
```
Three commands separated by semicolon, where `$` denotes the end of the input.
To go to the line before the last, there is no direct support in the sed command. Need to solve the problem by defining a new variable using `wc` to find the length of the input, and then doing operations on it separately.
```bash
sed -n '3p;5,10p;15,${N}p' f1
```
Alternatively, using awk:
```bash
awk 'NR==3 || NR>=5 && NR<=10 || NR>=15 { print $0 } ' f1
```

3. From the file f1 write out everything except lines 3, 5-10, 15 up to the last line.
```bash
sed '3d;5,10d;15,$d' f1
awk '!(NR==3 || NR>=5 && NR<=10 || NR>=15) { print $0 } ' f1
```
	
4. Write out only the lines representing the symbolic links from the f2 file
```bash
sed -En '/^l/p' f2
awk '/^l/ {print $0}' f2
awk '{if ($0 ~ /^l/) print $0}' f2
```
Note, inks start with letter l. It is possible to define REGEX in sed/awk using `/RE/`.
In awk, $0 is the whole line, and $1, $2, ... $n are the terms inside the line separated by default by tab and space. It is possible to use -F to change the delimiter.

To remove all spaces in the beginning of lines in a file
```bash
sed -E 's/^ //' input.txt
```
Following the pattern of substitution. `sed s/RE1/RE2/g`  Lazy, so sometimes we need to add `g` in the end so it doesn't `continue` after the first occurrence.

In the f3 file, replace the words "the" and "The" with the string "XXX". Verify with grep.
```bash
grep -E '\<[Tt]he\>' f3
sed -E 's/\<[Tt]he\>/XXX/g' f3
```

In the f3 file, replace the first word on the line with the string XXXXX.
```bash
grep -E '^[[:alpha:]]+\>' f3
sed -E 's/\<[[:alpha:]]+\>/XXXXX/'
awk '{if (NF > 0) $1="XXXXX" ; print $0}' f3
```
To replace the second word:
```bash
sed -E 's/\<[[:alpha:]]+\>/XXXXX/2'
```
The second to the end:
```bash
sed -E 's/\<[[:alpha:]]+\>/XXXXX/2g'
```

In the f3 file, replace the last word on the line with the string XXXXX.
```bash
sed -E 's/\<[[:alpha:]]+ *$/XXX/' f3
awk '{ $NF = "XXXXX"; print }'
```

Print the first word from every line.
```bash
awk '{print $1}' f3
```

Print the last word from every line.
```bash
awk '{print $NF}' f3
```

Print the line that has the most words from the file f3.
```bash
awk '{if (NF > max) {max = NF; line = $0}} END {print line}' f3
```

In file f3, replace the first word on the line with the string XXXXX using awk.
```bash
awk '{$1 = "XXXXX"; print}' f3
sed 's/^[^ ]*/XXXXX/' f3
```

In file f3, replace the second to last word on the line with the string XXXXX using awk.
```bash
awk 'NF >= 2 {$(NF-1) = "XXXXX"} 1' f3
```

What is the longest word in the f3 file?
```bash
awk '{for(i=1;i<=NF;i++) print length($i)}' f3 | sort -n | uniq -c
```

In the f3 file, replace the word before the last word on the line with the string XXXXX.
```bash
awk 'NF >= 2 { $(NF-1) = "XXXXX" } 1' f3
```