FROM centos:7

RUN yum update -y && \
    yum install -y epel-release

RUN yum install -y nginx

COPY ./.docker/nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./.docker/nginx/conf.d/symfony.conf /etc/nginx/conf.d/symfony.conf

RUN yum clean all

CMD nginx