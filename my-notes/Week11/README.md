### Lecture - 10.12.19

## Network management tool

### nmcli
* Will not be on the test
* Command line tool for user friendly management of most network features
* Very simple and cool for normal users
* RedHat and CentOS use this
* Chech man

**Hostname - 

### DNS servers - bind server
* Slightly easy to build form source xD
* After every url there is a dot that every tool places for us
* ARecord - the ip address of a url
* NSRecord - the next server that can answer the url qustion
* Zone - an array of records, at least one zone should be present
* named.conf
* Slave and master servers
* Slave servers just have copies of master servers and cant change the info
* Caching name servers - cache dns server - good for local caching
* Recursive DNS servers - prone to amplifing attacks
* nxdomain - no record domain
* fqdn
* The 13 . servers - the masters of all
