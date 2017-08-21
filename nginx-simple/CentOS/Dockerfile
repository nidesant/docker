# Dockerfile for a simple nginx image

FROM centos:latest
MAINTAINER Nick DeSantis <nidesant@gmail.com>

# Updates packages, installs latest version of nginx, and deletes default nginx.conf file.
RUN yum update -y && \
yum -y install epel-release && \
yum -y install nginx && \
rm -v /etc/nginx/nginx.conf

# Copies custom conf file from your current directory.
ADD nginx.conf /etc/nginx/

# Ensures that Nginx stays in the foreground so that Docker can track the process properly.
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

# Expose ports. 
EXPOSE 80
EXPOSE 443

# Start nginx service 
CMD ["nginx"]
