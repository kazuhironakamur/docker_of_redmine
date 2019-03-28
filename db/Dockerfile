FROM mysql:5.7
RUN apt-get update \
    && apt-get install -y vim
COPY my.cnf /etc/
#RUN 'mysqld --character-set-server=utf8 --collation-server=utf8_unicode_ci'