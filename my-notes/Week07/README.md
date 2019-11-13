### Lecture and test - 12.11.19

### Some test questions
pvdisplay
UMask - about files and directories, and which are valid
can we revert rm, rm -i
Bash and its regexes #
mouting as ro and rw - can we delete with them /proc
sed and awk cmd
/bin and /sbin
which is the slowest operation with hardisk
does hardlinks use inodes
boot loaders configs are stored where and how to conf
2>
raid, partitioning and lvm
when kill does want to kill
bin is not set in passwrd.. can they be changed
ps

## Bash, regex and text editors

**Check tail and tr command**

### AWK - Good materials in the presentation at  - check video
* operators

**Use the text editor which is mostly used in the infrastructure you are working**

### Piko
* Text editor for a mail client
* With academic license

### Nano
* Fork of Piko used for commertial purposes
* `^` is actually Cntr
* Usually bad, some for e.g. docker supports nano but not vim
* use nano -m file
* Do not open big files with it

**In linux the convention is that all configuration are written in ascii**

### Vi and Vim
* Good to have a How to quit massage
* Different key modes
* Normal mode - give commands to vim
* `i` - Changes to Insertion mode
* `esc` - switches to normal mode
* visual mode
* Used hjkl to move around and arrows

### Key binds - `:` +
* q - quit
* w -save
* Shift + G - go to end
* 42 + gg - go to the 42 row, works wit arrows
* d - delete - interesting specifiers
* shift + d - deletes form here to the end of the row
* q - undo
* :q! - the ! says that the operation should really be executed - interesting
properties - check video

### Visual mode - press b
* We can edit the current text
* We can copy
* v + shift +

### Visual block - control + v
* We can mark whole blocks of text
* Double ESC - gives us all

### Patterns
* press n - finds the next pattern
* press shift + n - find the previous
* search and replace - %, m, g

### Vim configuration
* Highly configurable
* vimrc
* Config on the go
* set numbers, nu
* set relative numbers

**vimtutor** - learn vim, cheatsheets in the repos, used by the hackman

**Many plugins**

**Plugins are bad idea for sys admins because usually we login into machines
with default vim**

### Midnight commander - mc
* No need to remember key binds
* Works with F1 to F12
* Useful when working with a lot of files
* Useful with bad file names
* Works with ssh