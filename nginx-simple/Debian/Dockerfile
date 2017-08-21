# Dockerfile for a simple nginx image on Debian

FROM debian:latest

MAINTAINER Nick DeSantis <nidesant@gmail.com>

# Updates packages, installs latest version of nginx, and deletes default nginx.conf file.
RUN apt-get update -y 
RUN apt-get install nginx -y 

# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

USER www-data

EXPOSE 80
CMD systemctl start nginx
