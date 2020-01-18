FROM hub.c.163.com/library/centos:latest

MAINTAINER Vance 937316808@qq.com

WORKDIR /home

# install nodejs version: 12
RUN curl --silent --location https://rpm.nodesource.com/setup_12.x | /bin/bash - && yum -y install nodejs

# install python3.6
RUN yum -y install python36 && mkdir /root/.pip/ -p

COPY ./pip.conf  /root/.pip/
COPY ./requirements.txt ./

# install python lib
RUN pip3 install -r ./requirements.txt

expose 8888
RUN mkdir -p /opt/documents
# startup jupyter, password: 123admin
CMD jupyter lab --ip=* --port=8888 --no-browser --LabApp.password='sha1:7cd6dcae0200:909fafc14ec0cd7d24787ec5eb9f440dc7fcb38c' --notebook-dir=/opt/documents --allow-root
