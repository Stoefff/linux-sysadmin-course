### Lecture 07.01.20

## HTTP

### The HTTP protocol
* Client inits the connection by requests
* Text protocol - text is passed around the server and client
* So passwords are passed around in plain text which is security issue
* TLS for security
* URL -
** Definition
** Scheme - PROT://user:pass@server:port/location(endpoint)?argument:value
** Example - http://pesho:gosho@google/553/location(hash for encoding)
* URI -

### Types of request
* CRUD
* GET
* POST
* PUT
* DELETE
* REST APIS

### Response
* Header
* Body, payload
** Text - plain text, HTML, JSON
* Server side executables called with CGI (Common Gateway Interface) with the
proper request, payload and authentication
** The CGI forks/spawns a new process

### Response types - return statuses
* 1XX - information response - the body gives us meta info - kinda rare
* 2XX - successful statues - defined by the convention of the current server
* 3XX - redirect statuses - self explanatory - gives the redirect location
** widely used to redirect to https or mobile version of the site
* 4XX - client cite error statuses - 403, 404, etc.
* 5XX - server cite error status

**Use properly these codes, not put all errors in code 400 for eg**

### Nginx web server
* Used also as a good load balancer and proxy
* Loggin files
* /etc/nginx
* Include mechanism
* Server directory in the conf files for all the needed behavior
* All the configuration should happen in the conf.d/ dir as a different file
* All changes happend after server restart
* Before every start of the server, we should do a conf spell check
* Regex as locations are supported
* Can specify CGI in the conf files (uwsgi in the case)
* ucgi have the crazies imperator log messages

### Apache web server
* Apache have a native support for executing certain languages, elimination
the need for CGI and thus being faster but less secure
* One basic conf file - for debian - /etc/apache2/apache.conf in redhat is diff
* When Apache is installed it creates new user, groups, etc in Linux when we
conf the server we should specify with which user and group the server prosses
should start
* Site enabled - the active sites which are handled, disable sites without
deleting the configuration
* Virtual Host - for which servers listen this virtual host - the same a nginx
directory
* Main difference - apache have many build in modules
* Static modules - build in executable

### How to master your knowledge  
* Test the web server Curl localhost 80 - hello world html
* Test the web server with a CGI component that returns the params passed to it
* Make 2 virtual host
* Spawn Wordpress site on it with mysql for the real legends

