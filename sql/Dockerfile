FROM mysql:5.7
ADD mysqld.cnf /etc/mysql/mysql.conf.d/
ADD ry_20210731.sql /docker-entrypoint-initdb.d
ADD quartz.sql /docker-entrypoint-initdb.d
ENV MYSQL_ROOT_PASSWORD=root MYSQL_DATABASE=ry-vue
RUN apt-get update \
    && apt -y install curl \
    && curl -s https://packagecloud.io/install/repositories/akopytov/sysbench/script.deb.sh |  bash \
    && apt -y install sysbench

VOLUME /var/lib/mysql
EXPOSE 3306