FROM centos:7

RUN yum update -y && \
    yum install -y epel-release

RUN yum install -y httpd

RUN echo "ServerName localhost" >> /etc/httpd/conf/httpd.conf
RUN yum clean all

CMD httpd