Demonstration of how docker can be used to serve static files.

The application is seperated into two containers:  
One containing the static files.  
The other running a web server serving the static files.

In order to run, Docker and Docker Compose have to be installed.  
Then run `docker-compose up`.

Example for how to create both containers without Compose:
```
docker run -d --name static -v /path/to/static:/usr/share/nginx/html busybox
docker run -d --volumes_from=static -p 8080:80 nginx
```
