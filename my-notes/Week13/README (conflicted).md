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

### Apache web server

