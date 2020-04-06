FROM httpd:2.4

RUN apt-get -yqq update \
     && apt-get -yqq upgrade \
     && apt-get clean \
     && rm -rf /var/lib/apt/lists/* ;

# Copy apache vhost file to proxy php requests to php-fpm container
COPY .docker/apache/moodle.apache.conf /usr/local/apache2/conf/moodle.apache.conf
RUN echo "Include /usr/local/apache2/conf/moodle.apache.conf" \
    >> /usr/local/apache2/conf/httpd.conf