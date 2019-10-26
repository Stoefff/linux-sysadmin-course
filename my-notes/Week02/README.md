## Partitioning and file systems - 08.10.19

Distribution - combination of kernel and user space
MBR - 1 sector - 512 bytes

In LINUX all partitions are logic by default

Its good to keep the boot loader and the kernel on a separate small (500 MB)
partition

There are always 4 primary partitions by default

### Primary and logical partition
The primary partition are described in the MBR so the system can boot
from them

**Good partitioning can solve the problem with adding new physical devices
and the following resize of the logical partitioning**

When we have more than 8 GB of RAM - **do NOT touch the swap**

### Pseudo File Systems
Not Real files, rather representation of system info that the kernel gives
examples: tmp, proc

### File Systems - in the case
2 parts:
* Super block - contains inode table and is copied many times for redundancy
* Data block - the content of the file

### inode - meta data for a file
Contains 12, 13 data blocks, the 11 contain other inode, the 12 contains inode
of inodes and so on

### Symlink and hardlink
* Symlink - shortcut file, contains the path to the file, uses both super and
data block
* Hardlink - second name for a file

### LVM1 & LVM2
Logical Volume Manager
Lame Vertical Move

The holy abstraction of logical disks
We do this so we can be smart when resizing with more physical disks

Consists of:
* Volume Groups - there can be from 1 to 99 VG
* Physical Volume - a VG can consist of 1 to 256 PV in a VG - same as partition
** PV size is from 512 MB up to 2 TB
* Physical Extend - a PV can consist of 1 to 65 534 PE in a PV
** PE size is form 8KB up to 512 MB

The idea:
We connect Physical Volumes in Volume Group and from it we create a Logical
Volumes which we use (for directories such as boot, usr, etc?)

### Snapshots

### Thin provisioning
We trick the system to think there is logical volume that is way more big than
in the actual hard drive

### RAID

### Schemes