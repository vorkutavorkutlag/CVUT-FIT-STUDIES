# Permissions

Permissions are an important topic in Unix Operating Systems, a crucial component which allows multi-user compatibility without conflict or intrusion.
#### User Account
A user account must be created before it can be used.
The following information is represented in an account.
- User name
- User ID: `UID` (Where `UID` = 0 represents admin)
- Primary Group: `GID` (User belongs to at least one primary group)
- List of secondary group IDs (optional)
- Comment (description of the user)
- Home directory (working direct is set to home directory after login)
- Login shell
- User password

The users are all stored in a user database. The location varies.
![[Pasted image 20251202085529.png]]


### Classic Model of Security Access

We have seen this when encountering the file/directory. Running the command `ls -a`:
![[Pasted image 20251202085732.png]]
![[Pasted image 20251202085758.png]]


Processes have attributes (`EUID, GID_1, ..., GID_n`)
And so do objects (`OUID, OGID`)
The child process inherits the identity from the parent.
![[Pasted image 20251202090855.png]]

New processes may be created by system call `fork()` and `exec()`. Only when we have some special permissions in a binary file is the permissions inherited from elsewhere. Usually it is from the parent.

We may remove or add permissions (given we have the necessary permissions).
Executing `chmod` will have that effect. For example, `chmod g-w f.txt` (removes).
![[Pasted image 20251202091719.png]]

The user file creation mask defines permissions of new files and directories and it is inherited from the parent process. It can be printed by the command `umask -S`.


## Find Command

Powerful tool for... the name says it all. It contains the following flags:
- `-name <pattern>`  ... true if the pattern matches the basename
- `-regex <pattern>` ... true if pattern matches the whole path
- `-type [d,f,l,b,c]`... true if the type is of the given type.
That being: directory, file, link, block, character.
- `-inum n`... true if the file has inode number n

For example, to print all of the items from home directory recursively:
```bash
find ~ 2>/dev/null
```
Print all items from your home directory (recursively) with suffix ”.txt”:
```bash
find ~ -name "*.txt" 2> /dev/null
find ~ -regextype posix-extended -regex "^.*\.txt$ " 2 > /dev/null
```
Do the same thing but only for regular files:
```bash
find ~ -type f -name "*.txt" 2> /dev/null
find ~ -type f -regextype posix-extended -regex "^.*\.txt$ " 2 > /dev/null
```

It is possible to run other tests on these commands.

Everything up to find will be in the test.
Archiving and Processes will not be in the test.

The End.
Finale.