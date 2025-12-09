[[COURSES/BIE-PA1/LECTURE 18]]
When allocating new memory, and invoking `sizeof`, you can always dereference the uninitialized pointer you may be using, as it will not actually access the memory, but rather only the type, which is static.
