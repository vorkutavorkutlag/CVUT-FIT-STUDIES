[[COURSES/BIE-UOS/LECTURE 2|LECTURE 2]]
# INTRODUCTION IN UNIX OPERATING SYSTEM

Unix is now a trademark, as there isn't a single \`Unix\` operating system. Unix-like systems are based off of the core attributes and philosophy of the operating systems.
In the beginning it was designed as a multi-user and multitasking system, hence the emphasis on concurrency and permissions prevalent.
The source code for the original Unix is open-source, and it was rewritten into C for portability, being the reason it may also work on different computer architectures.
GNU project is a series of tools and interface for UNIX-like operating systems.
The Linux distributions have been born from UNIX.

### UNIX architecture is built as such:
At the very core is the hardware, which includes physical components such as GPU, CPU, keyboard, mouse, monitor, etc. Additionally, in the same layer there is some Firmware that comes along 'engraved' within the hardware, apparent in concepts such as BIOS/UEFI.
Above that is the Kernel, the direction communication of the software with the hardware, passing of instructions and computations, writing or reading data, etc. Above that is the UNIX API, meaning there exists input situated right on top of the Kernel, giving very intensive control over the system and its most integral components.
Above is the Libraries which have been either preinstalled or installed by the API, which contain the basis for other processes that may be running on the machine. On top of the libraries sit the system processes, and beside, the users and the users' individual processes.

### UNIX properties:
UNIX is designed as a multiple user OS, wherein multiple individuals or programs may access it at the same time, within their respective limitations. All non-kernel software is organised into separate, kernel-managed processes. Multiple processes may run at the same time.
90% of the kernel is written in C, making it widespread and compatible.
Built-in networking including TCP/IP/NFS/RPC, etc.

### Shell
Direct interface between the user and the kernel.
The shell is a simple application running at the terminal, the goal of which is to interpret the commands written by the user, and execute them with respect to additional instructions such as flags or arguments. You may also define some variables and other programming features for more complicated tasks.
Shell implementations include mainly the Bourne Shell, featuring Pascal-like syntax; Bourne again shell (`bash`) is the most widespread shell, as it is the one used in most Linux distributions, though there are also different implementations such as sh, ksh, zsh, etc.
Additionally, C-shells are shells that exist based on the C language and are similar in implementation (for example, csh, tsch, etc.).

### Environment Settings
We can define variables that control the system and application behaviour. They are local, meaning each user has his own environment and his own variables. They can be saved in configuration (config file local to each user) => environment is remembered.
- For example, the system time is absolute (GMT)
- User can define a value of TZ (timezone) and all displayed data will be recalculated