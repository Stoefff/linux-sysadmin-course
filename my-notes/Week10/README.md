### Lecture - 03.12.19 - not recorded

## Package management

### History
* Long time ago in order to distribute code the only thing to do was to share
the code
* With many files came a lo of dependency


### Make
* DSL - domain specific language - specific language optimized for the specific
tasks
* Describes algorithm for building/compiling the program
* Target - by default it calls all
** all
** clean
** install
* Smart rebuild

### CMake
* Generates Make - abstraction of Make

### Makefiles

### Configure files
* The next level of abstraction
* Check if all needed header files are present
* Check where are needed header location in order to link them
* Config.autoconf - DSL for checking some custom conditions for the build

**configure make make install - solves most of the problems**

### GCC crash cource
* -O2 - optimization level
* -o output file name
* patches - created with diff -up between 2 files and then the output is dumped
into the patch file, then this file is used wih the patch commands for patching
* The patch file contain both files - the one needing patching and the one that
contains the new info
* p flag - ignore the p flag number of directories - if some directories are
problematic for patching just ignore them

### Version control systems

### Package - foor-1.0.tar.gz
* tar - Archive format, for the Tar achivator
* gz - compression format
* tar xfvz foo-1.0.tar.gz - декомпресирай и компресирай
* ./configure
* make
* make check - Muri special target
* su
* make install

### ./Configure - what happends
* Also checks if the needed software is present
* Handles file dependency e.g. file linking in C and optimizes the build
process for the current machine with
* Creates the Makefile
* autoconf - generates the configure files if they are not present with the
configure.ac
* support -
**configure and makefile should not be touched by hand**

**Slide 10 is mandatory for the test**

### Makefile
* Here lies the scripts that build the program
* Make uses this file

### Package management systems - low levels
* RPM
* dpkg
* does not handle dependency errors but knows about them
* Contains the package - binaries, not source !
* scripts - the configuring some things before an action with the package
happens or just call them config files
* meta data - list dependency, version, architecture
- noscripts rpm flags - is use full when upgrading on big server without
restarting the whole system if such scripts are present in the package

### High level wrappers
* yum or now  - rpm
* apt - dpkg

### Repositories
* The package manager should be instructed in which repositories the packages
are found and downloaded from
* in Debian there are 2 types of packages - normal and source
* By default Debian does not allow proprietary code packets and this
should be done manually in order to allow drivers such as Nvidia and Ethernet
drivers
* Security repos - security fixes and patches

**yum search vs apt-cache search: yum searches for packages from the repo
sources (ftp servers) in order to upgrade them for e.g. and apt searches local
indexes of the repos, and if you want to upgrade these indexes we should do
apt update - apt is not dependent that much on the internet**

### Remove vs purge
* remove - deletes the package but leaves the configuration
* purge - deletes everything - and package and all of its configurations
