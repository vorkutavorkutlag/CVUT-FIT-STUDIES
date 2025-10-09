The tutorial started with a short practice about meta characters and parsing, different methods to write:
```sh
date +"Today is %A, &d.&m.&Y \(week &V\).%nThe time is %T [%Z]."
```
You could replace the quotation marks with single quotes, or, if you don't want to use quotes at all, you can drop them and put a backslash between every space to cancel their meta (in this case, their separative property). Since round brackets have special meta meaning, they should be cancelled by the backslash as well. Square brackets do not have any meta meaning, therefore there is no need to use it.

We repeated different quoting characters, those being the backslash `\` which cancels the meta of the character in front of it; the single quotations, that everything within them is a raw string; quotation marks, everything in which is a raw string except backslash, apostrophes \`, and $ {$Variable, $(Command Substitution), $((Expression))}.

It is important to note that sometimes evaluations of commands will return values with spaces, and so using quotation marks around evaluations usually solves some formatting problems.

We repeated Command Separators, including:
- `cmd1 | cmd2` - Run both commands in parallel, actively passing output of cmd1 into input cmd2 via channel.
- `cmd1; cmd2` - Sequential. First run the first command and wait for it to finish, only then run the second one.
- `cmd1 & cmd2`- runs the second command in parallel in a subprocess.
- `cmd1 && cmd2` - sequential with conditional execution (if cmd1 was successful). Not to be confused with single ampersand, which is parallel running.
- `||` - conditional execution of the pipe (`|`) operator. allows you to execute a command only if the preceding command fails.



