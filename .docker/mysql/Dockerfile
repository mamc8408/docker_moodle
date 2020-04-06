FROM mysql:5.6

LABEL maintainer="Mario Mendoza"

COPY .docker/mysql/mysql.cnf /etc/mysql/conf.d/mysql.cnf
WORKDIR /var/www/html
RUN chown -R www-data:www-data /var/www/html

EXPOSE 3306
