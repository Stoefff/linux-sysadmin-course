### Lecture - 22.10.19

### Special Permission
* Sticky bit
** For file does nothing
** For dirs - make all files only deletable only by file owners
* SUID
* SGID

### Extended file attributes
Key-Value store of 5 sections
Used in very special occasions

## Linux Process

### PID
Unit is with number 1

### Kernel vs User space
The memory of the machine is divided into 2 parts:  
* Kernel spaces can touch everything
* User process can ask the kernel for tasks

### Segmentation fault
When a programs tries to access other process memory

### Guest process
Actually have more rights than users

### Fork vs Exec a process
* Fork - Duplicates the current process
* Exec - Changes process without changing PID

### Foreground vs Background
* Std::out of a process is attached to terminal when in foreground

### System signals
* Cntr + C - ^C is a system process interrupt
* Cntr + D - Send end of line character

### CMD
* jobs -
* fg - set foreground
* ps
* pidof and pgrep
* top

**SETSID - check man**

### Deamon
They closed their stream IO and are optimized for background work

### Thread vs Process
* A process can have many threads
* These thread share the memory of the process
* The kernel schedular makes decision which threads can be exec parallel

### Process security
Done by ids - Check video for details
* Real
* Effective - scheduler
* Saved - check the previous user

### Capabilities
Instead of giving root access just a one easy tasks, cap were invented
**man 7 capabilities** for the hard tasks of children/parent caps with masks
P is process F is file in the man

**There are many security issues connected with the inheritance of process and
capabilities**

### Process priority
Done with priority level, nice level
Context switching should be with constant time

### Communication between process
* name pipes - on the on end there is producer and the other consuming
* shell pipes
* unix sockets - bi-direction pipe but with support for multiple process
in and out - best method