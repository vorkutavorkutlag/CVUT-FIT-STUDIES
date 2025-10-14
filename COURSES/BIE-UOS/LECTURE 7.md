[[COURSES/BIE-UOS/LECTURE 7 - PART 2]]
Next week there will be a small test in the beginning of the tutorial (week 5).
Small 5 minute test with one question within the LearnShelll system (sent link on email).

Create directory, create file, copy directory/file...

Today or tomorrow homework will be given on LearnShell to get familiarized on the system.
There is no limit for uploading solutions.


##### Continuation of Command Execution

Other than commands which are shell-builtins such as `echo`, most commands' executables are stored in a directory which is present in the $PATH. You may execute them by calling their name (which is present in the directory in the $PATH), their full path, their relative path, etc.
You may use `type` and `which` commands and pair them with a command to see whether if it is a shell builtin, or, if not, where it is stored in the system.


##### Shell variables

Local shell variables: The variable is defined only in the current shell.
Definition: `NAME=VALUE`

Environment Shell Variable: The variable is defined in the current shell and all its descendants.
Definition: `export NAME=VALUE`

The reason we need environment variables is mostly due to the multiuser aspect of unix. When a user logs in, the system reads the configuration files and sets the environment appropriately to the user.

To print the value of a variable, use echo with the dollar sign to evaluate the variable.
To print the list of all variables (local + environment), use `set` command.
To print the list of all environment variables, use `env` command.

###### Built-in shell variables
`HOME`: home directory
`PWD`: current working directory
`PS1`: prompt definition 
`PATH`: list of directories for command searching

`0`: program name
`1,..,9`: command line arguments
`#`:  number of command line arguments
`$`: process ID of current shell
`?`: exit status of the last executed command

They are described in the manual page of the shell.
`man bash`

To delete a variable, setting it to an empty string is not enough. To truly delete it, you may use the `unset VAR` command.
To see if a variable exists or not, you may use `declare -p VAR`

