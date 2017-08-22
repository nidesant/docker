# Creates Python2.7.10 image for a python  dev environemnt on CentOs 7.x

FROM centos:latest

MAINTAINER Nick DeSantis <nidesant@gmail.com>

# Installs dependencies
RUN yum update -y && \
yum groupinstall development -y && \
yum install -y \
openssl \
openssl-devel \ 
bzip2-devel \
gcc \
tar \
wget \ 
zlib-dev \
git \
sudo \
sqlite-devel

# Downloads and installs Python
RUN mkdir /tmp_python && \
cd /tmp_python && \
wget --no-check-certificate https://www.python.org/ftp/python/2.7.10/Python-2.7.10.tgz && \
tar -zxvf Python-2.7.10.tgz && \
cd /tmp_python/Python-2.7.10 && \
./configure --prefix=/usr/local && \
make && \
make altinstall && \
export PATH="/usr/local/bin:$PATH"

# Installs pip
RUN yum install python2-pip.noarch -y

# Removes tmp install path and installs virtualenv
RUN pip install virtualenv && \
python -V

# Default command
CMD ["bash"]
