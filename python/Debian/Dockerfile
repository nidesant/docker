# Creates Python2.7.10 image for a python  dev environemnt on Debian latest. 

FROM debian:latest

MAINTAINER Nick DeSantis <nidesant@gmail.com>

# Installs dependencies
RUN apt-get update -y && \
apt-get install -y \
build-essential \
gcc \
tar \
wget \
python-pip \ 
libadns1-dev \
python-dev \
libreadline-dev \ 
libsqlite3-dev \
libssl-dev \
libbz2-dev \
libncurses5-dev \ 
libdb-dev \
libgdbm-dev \
zlib1g-dev

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
#RUN cd /tmp_python && \
#wget --no-check-certificate https://bootstrap.pypa.io/get-pip.py && \
#python get-pip.py 

# Installs virtualenv
RUN pip install virtualenv

# Creates working directory
ADD . /code
WORKDIR /code

# Default command
CMD ["bash"]
