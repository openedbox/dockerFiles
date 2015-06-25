FROM centos:6
MAINTAINER openedbox "openedbox@qq.com"

RUN yum localinstall http://dev.mysql.com/get/mysql-community-release-el6-5.noarch.rpm -y
RUN yum install mysql-community-server mysql-community-client  -y;yum clean all

RUN /etc/init.d/mysqld start &&\
    mysql -e "grant all privileges on *.* to 'root'@'%' identified by 'new.1234';"&&\
    mysql -e "grant all privileges on *.* to 'root'@'localhost' identified by 'new.1234';"&&\
    mysql -u root -pnew.1234 -e "show databases;"

EXPOSE 3306

CMD ["/usr/bin/mysqld_safe"]
