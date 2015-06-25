FROM registry.docker.avcdata.com/centos:6
MAINTAINER openedbox "openedbox@qq.com"

RUN yum install tar -y;yum clean all
ADD http://file.avcdata.com/linux/jdk-8u25-linux-x64.tar.gz /usr/local/
workdir /usr/local
RUN tar zxf jdk-8u25-linux-x64.tar.gz
RUN rm -rf jdk-8u25-linux-x64.tar.gz
ENV JAVA_HOME /usr/local/jdk1.8.0_25
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin
