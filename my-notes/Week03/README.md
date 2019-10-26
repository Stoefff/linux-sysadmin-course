### Lecture - 15.10.19

### Boot loaders
Idea - MBR are static, cant change boot directory or support for many boot places  
Boot loaders change that and add flexibility
* Lilo - if we make a mistake in the conf file its a GG
* GRUB - add an interface and allows for mistake changes
* PXE - network boot through tft server

### Initial RAM disk
Makes boot loaders work with LVM, RAID, etc
When we boot the OS, the machine should execute an Init script which starts
the LVM or/and gets needed drivers so the machine could work

**After that happens we should specify which is our root so it run its magic
mount, unmount swap / and /mnt, so it can free the Init from the RAM**

### Init - the first program the kernel uses
1. Loads the drivers
2. It should run some other software in order to make the user space multy threaded
3. Starts the physical terminals
4. Starts system helper programs - sets up the network conf, I/O services
like mouse, keyboard  

### 5 Inits systems
* Init
* Runlevels - group of scripts that are essential
** Level 0 - halt - shutdowns the system
** Level 6 - reboot
** The other levels - defined by the distros

### System 5 - only supported by slackware
Can be run sequentially and parallel

### System D - the other distros
* Mostly parallel
* Administrates many many things to the point its bad and annoying like the
network process
* Does not follow the KISS model of Unix

### Terminals
* Physical terminal - tty or Ctrl + Alt + F1 to F6
* Virtual terminal - the terminal which we use - terminator, etc

### Deamon vs service
* Deamon - defined as a background process with logs and defined way to
communicate
* The service is the same as deamon in the context of Linux

Config files are in /boot

Config for GRUB2 are not changed by hand, templates add ons required  

Hackman advices writing configs by hand

**Check how Umask works**