### Lecture - 17.12.19

### Questions on the test:
* How to install DHCP on Debian/RedHat
* Named conf vs dhcp.conf - in named conf there are always ; after a closing
bracket

## DHCP

### Config
* DHCP allows PC to boot from network commands
* Timings
* Define all the networks - support for many networks
* Pools JUST from the defined networks
* Support for multiple static IP adresses on a PC
* Windows allows for multiple static IP but Linux does not out of the box

## Cron deamon
* Does a specified tasks from a period of time
* Wakes up every mine
* Smartly handles time changing up to +-3 hours and does not fucks up the
scheduled tasks
* Viksi Cron
* Envrimental variable for the time period
* Check man

### Configuring crom
* /var/spool/cron/tabs - define users and tasks
* /etc/cron.d - specifies cron jobs but does not understand users
* Lowest range is 1 minutes
* , - logical AND
* - defines range
* /number - every number minutes
* support random interval sleep of a job
**crontab.guru for spell checking**
**Ubuntu does not come a mail client - should install Postfix for that**

### Crontab
* Command for configuring chrom
* chromtab -l - chrom jobs for the current user
* /etc/cron/hourly, /daily, /monthly
* SHELL var - the shell that executes the tasks
* Path var - the path for searching the task commands
* Batter not to std::cout the tasks if we have many task
* Generally be very careful with what you do with crontab especially with emails
* Check man

### OS Locking mechanism
* A mechanism that allows only one job to be executed at one time
* Semafors - have problems with multu core processors - because queues can
be wrongly re-arranged
* File locking
* Massage queue

### at and atq
* at - Do a specific tasks ONCE after a certain time
* Supports load average
* atq - list all the jobs
* Conf files - /var/spool/cron/atjobs
* check man

### SSH
* Command for secure remote access of a machine
* Diff-Helman key exchange, **NEVER** use just password for autentication
* Disable passwords - Password Autentication no and PAM no
in /etc/ssh/sshd_config
* OpenSSH server
* ssh key gen
* ~/.ssh/autorized_keys ? - store all the keys
* Supports graphical remote access - X11 with -X
* Client site config - ~/.ssh/config - defining aliases for hosts, ports, etc
* Escape sequence - Enter + . ??
* SSH is a secure TLA or SSL tunnel
* Proxy, reverse proxy, X forwarding