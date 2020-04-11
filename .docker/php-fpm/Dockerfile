FROM centos:7
RUN yum update -y && \
    yum install -y epel-release gcc make autoconf 

RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm && \
    yum -y --enablerepo=remi,remi-php56 install php php-common && \
    yum install -y yum-utils git unzip && \
    yum -y update
 
RUN yum -y --enablerepo=remi,remi-php56 install php-fpm php-cli php-pear php-pdo php-mysql php-mysqlnd php-pgsql php-sqlite php-mbstring php-mcrypt php-xml php-simplexml php-curl php-devel
RUN useradd -M -d /opt/app -s /bin/false nginx

RUN mkdir -p /run/php-fpm && \
    chown nginx:nginx /run/php-fpm

RUN mkdir -p /var/lib/php/session && \
    chown nginx:nginx /var/lib/php/session

COPY ./.docker/php-fpm/php-fpm.conf /etc/php-fpm.conf
COPY ./.docker/php-fpm/www.conf /etc/php-fpm.d/www.conf
COPY ./.docker/php-fpm/php.ini /etc/php.ini
COPY ./.docker/php-fpm/xdebug.ini /etc/php.d/xdebug.ini

RUN pecl install mongo-1.3.7
RUN pecl install xdebug-2.5.5
RUN mkdir -p /var/log/xdebug_profiler_logs

RUN yum clean all

CMD php-fpm
 