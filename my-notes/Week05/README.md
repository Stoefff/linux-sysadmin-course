### Lecture - 29.10.19

### More process ICP
* Shared file system?
* Shared queues
**ICPS man page for more info**

## Shell and bash

### Shell
The first program that is run after a logic is complete
Interprets IO better than the old dumpster terminals
**Check video again**

## Bash
* Born again sh
* Derived by sh shell
* Adds syntax for running many commands one after another
* Unix is still with csh(c style shell)
* Adds file IO

### Environment
* Comes from the OS, not the shell
* Describes the resources
* Its like a 2D arrays - in the first column there are environment variables
and the other columns are the parameters of it

### Tricks
* Cntr + R - search from front to back
* Cntr + S - search from back to front
* Alt + B - readline() lib bind to go one word back
* Alt + F - readline() lib bind to go one word forward
* Cntr + стрекличка - bash bind for the ^
* Export
* which
* whoami
* type
* declare
* echo $$
**Bash history is not a security механизъм**

### Enviromental vars vs bash vars
When starting a new process:
* Env vars are inherited
* Bash vars are not

### $PS1, $PS2, $PS3 and $PS4 - check video

### $Path
* Bash searches for commands and stuff in the directories specified in it
* Searching is done from left to right
* This var is very important
* Is the path is empty, we can run the command with its full path, and from
Bash 4 it can search in the current directory
* Path should be configured by us, otherwise sec issues could arise

### Globing, globe expansion
* * adds all possible strings - front and back  
* ? is replaces ONE character with all possible

### Alias - Shortcuts
Making long command to have a shortcuts

### Configuration files
* /etc/.profile
* /etc/bash.bashrc
* /home/stoefff/.bashrc
**rc - run command**

### Bash scripts - check video
* Alias or just vars
* Glob expansion
* Base expansions - like list with a lot of added functionality
* Functions
* Tilda - the home directory, ~+, ~-
* vars - how to reference vars - with $
* string substitution, and default values
* %% - cuts at the back
* ## - cuts at the front
* // and / / - replaces
* One special symbol - non greedy , Double special symbol - greedy
* Process substitution - allows us to run a command which params are also cmd
* Piping and subshell
* For structures - instead of
* " " - interprates the strings as a whole - edge cases
* pre functions
* $@ - arrays in bash, very deep and bad
* if statement - after every if there is a test **check man**
**Bash in most cases is case insensitive**
**Backticks are for old people**
**Bash scripts with more than 100 line of code, should be written in other
scripting lan - perl, python**

### @ vs * in expansions
* * is interepretesd as a whole thing
* @ gets us all the elements

### Piping orientation
* Left to right evaluation
* But because all thing or the right are completed in subshells, the return
is that of the thing on the right 