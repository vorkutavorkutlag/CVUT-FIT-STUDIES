[[COURSES/BIE-PA1/LECTURE 16]]
## Pointers

Pointers address abstraction in a high-level computer language. Pointer to type T represents a memory address where value of data type T is stored. Pointer declaration is as follows:
```c
T * ptr
```
Variable `ptr` represents an address. Like other local variables, when uninitialized the behavior is undefined. To assign it to a variable x of type T:
```c
ptr = &x;
```
The unary prefix `&` is called a reference. The result of the operation is a pointer, an address of the variable of type T in the memory. 
An address is indeed an integer that gives the position in the memory. The position is counted in bytes starting from the beginning of the memory space. Simplified – if CPU sends address bit pattern to the address bus, the memory chip accesses the corresponding memory cell.
The actual address value of the pointer is seldom important.
To dereference a pointer, as in, access its actual value rather than its address, the dereference pointer `*` must be used.
```c
(*ptr)
```

The effect of messing with the compatibility of pointers is heavily reliant on the architecture of the machine, the endianness of of the processor, and other factors.
![[Pasted image 20251103153906.png]]

##### `nullptr`
`nullptr` pointer - a special address indicating that a pointer points "nowhere". `nullptr` is used to signal special cases (e.g., an operation failed). It is the only value of type `nullptr_t`. This data type is implicitly convertible to any pointer type and to integers (of value 0). An attempt to dereference `nullptr` results in program crash.
Accessing memory that does not belong to you will terminate the program with segfault.


### Output parameters

Input parameters cannot be used to pass values from the callee to the caller. In C, pointers to these variables must be used. The caller passes pointer (memory address) of the variable which will act as the output parameter. The pointer (memory address) is passed as a regular input parameter. The callee may use the memory address to access the output parameter, it may both read and write it. the pointer (memory address) parameter is disposed on return. However, the value in the output parameter remains.