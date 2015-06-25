FROM centos:6
# 签名啦
MAINTAINER openedbox "openedbox@qq.com"


RUN yum clean all
ADD node-v0.12.4-linux-x64.tar.gz /tmp

RUN mv /tmp/node-v* /tmp/nodejs
RUN mv /tmp/nodejs /usr/local
ENV NODE_HOME /usr/local/nodejs
ENV PATH $PATH:$NODE_HOME/bin
