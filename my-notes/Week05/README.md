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
* which - locates where command is stored
* whoami - displays the current user
* type
* declare
* printenv - self - explained
* echo $$
**Bash history is not a security механизъм**

### Enviromental vars vs bash vars
When starting a new shell process:
* Env vars are inherited, they are gather by the root shell after system boot
* Bash vars are not - they just the vars in the current running shell process

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


### Command line arguments
Starting new shell session foo.sh arg1 arg2 gives us two arguments
The arguments can be access by shell with $0 - foo, $1 - arg1, $2 - arg2

### Special symbols
* `$` - variable(maybe more like its value)
* `$0 - $n` - the cmd arguments passed
* `$#` - number of arguments
* `$@` - list with all the parameters
* `$?` - the return status of the last executed program
* Default Env vars

### Enviromental variable
* `$PATH` Executable search path
* `$PWD` Path to current working directory
* `$TERM` Login terminal type (vt100,xterm)
* `$SHELL` Path to login shell (/bin/sh)
* `$HOME` Path to home directory (/home/foo)
* `$USER` Username of user
* `$DISPLAYX` display name (station2:0.0)
* `$EDITOR` Name of default editor (ex)
* `$VISUAL` Name of visual editor (vi)

### Constructs
* And list  - `cmd1 && cmd2` - executes continues if the current cmd returns 0
* Or list - `cmd1 || cmd2` - executes continues if the current cmd return !0
* test - `test EXPRESSION [EXPRESSIONS]`
* if statement - `if ... then ... elif ... else ... fi` - **Do NOT miss fi**
* case - `case .. pattern1) .. pattern2).. * ) .default. esac`
* for loops
** `for VAR in 1 2 3 do .. done`
** `for ((EXP1 , EXP2, EXP2)) do .. done`
** break and continue are supported
* while loops - `while [condition] do .. done`

**(command1; command2; command3;) - The parentheses are threated as a subshell**

### Process substitution and file descriptors
* <(cmd) - refer by filename to process output
* >(cmd) - refer by filename to process input - what?
* command < input.in - pass the input.in as a input of the command
* command > output.out - write the output of the command in the output.out file
* read a b c < <(echo "one two three")

### Piping
* cmd1 | cmd2 - cmd2 output will be passed as input of cmd1

### Substitutions -  : :
* Front - `#*`
* Rear - `%%.*`
* Regex - //

### Functions
Syntax: function_name () {command...}

### Expansions
* Parameter
* Globe

### Bash scripts - check video
* Alias or just var
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