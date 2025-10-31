
There was supposed to be a test today, but due to technical issues we will be proceeding without 

Practicing creating variables and using the date command with its formatting.
```bash
MyDate=$(date +"%d %m %Y") # dd mm yyyy
MyTime=$(date +"%H %M %S") # hh mm ss
```
Then, creating directories and files with these names.
```bash
mkdir "$MyDate"
cd "$MyDate"
touch "$MyTime"
```
Note that it is important to use the quotation marks as to not pass multiple arguments to the command. Additionally, to remove several folders, you may use `rmdir` and then the expression (i.e., `*` for removing every directory in cwd).
Then, generating random numbers and putting them into files. `$RANDOM` is an environment variable that gives a random value each time it is called or read.
```bash
echo "$RANDOM">a.txt
echo "$RANDOM">b.txt
```
These two files will have different values.
And to find their sum:
```bash
SUM="$(($(cat a.txt)+$(cat b.txt)))"
```
command evaluation and arithmetic evaluation

Then went over `df` and `du` commands. `du` with flag `-s` gives summary in one line.

After than, a practice including creating directories, and copying files from different directories to this directory using the `cp` command and incorporating expressions. For example: 
```bash
cp -r /etc/*.$SUFFIX /tmp/uos/conf/
```
Will copy all `.conf` files from /etc/ to the folder that we specified.

Then, to move those whose length is longer than a certain length to some place, and the rest elsewhere, we may either write a script with `wc`, or use pathname expansion:
```bash
ls ???????????
```
This is files with exactly 10 characters
```bash
ls ???????????*
```
This is files with 10 or more characters.

```bash
mv ??????????* '.../>=10'
```
after that, only the shorter names stay in the conf directory. Then:
```bash
mv * '../<10'
```


NEXT TEST (START OF NOVEMBER) WILL INCLUDE FILTERS FROM TEE TO PASTE

