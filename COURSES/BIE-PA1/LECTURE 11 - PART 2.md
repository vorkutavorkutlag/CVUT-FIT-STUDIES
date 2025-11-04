[[COURSES/BIE-PA1/LECTURE 12]]
# FUNCTIONS

A function is defined from its name, its return type, and its parameters.
Every function counts as a scope, thus, for example, variables within it are no longer defined outside of the function (i.e. in `main`).
A function, by definition, is a subprogram which solves some partial problem. Function body is a block which is executed when the function is called.

Note: If splitting code from main into a function, and you return at some point in that function, you might want to use `exit(int code)`  in the function to exit the program.

`exit()`, although useful as an idea, is the wrong way to do it.
The `exit()` function is a last resort option to terminate the program. It is to be used when immediate termination is the only safe option (e.g., the program controls a HW which broke down). It is usually rash to use exit() to handle invalid input.
- the user may be prompted to fix the wrong input
- the input may be optional
- the program may run some critical computation
- the status of the computation needs to be saved
- etc
In general, low level functions do not know the big picture. Thus, error handling is usually done by some higher level function (i.e. callers, main).
Errors are usually reported to the caller by means of return value or by means of exceptions. (C++)

Functions, when called with a parameter, will copy the parameter from the actual parameter. The assignment copy may perform type conversion, just like ordinary assignment.

When writing the parameters for a function, you may use `...` - ellipsis. 
Ellipsis denotes more unspecified parameters. There parameters are accessed via `va_*` macros from `stdarg.h`. The user must ensure that the expected and actual parameters match. Otherwise the behaviour is undefined.

```c
int sum(int count, ...) {
	int res = 0;
	va_list args; va_start(args, count);
	while (count-- > 0) res += va_arg(args, int);
	va_end(args);
	return res
}
```


Per need, you may declare a function without a body, and then define it at a later point in the function code.

The parameters are input parameters. They are used at the time of the call, and then the relation is separate.

To return more than one value in a function we use output parameters. C does not natively support it, but we can use pointers (next lecture);

Don't use global variables, see errno!

Alternatively, we may pack multiple values into one box - structures and its members.