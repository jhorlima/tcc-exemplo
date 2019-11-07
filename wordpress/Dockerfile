FROM wordpress:latest

ENV XDEBUG_PORT 9000

#RUN sed -r -e 's/\r$//' /usr/src/wordpress/wp-config-sample.php \
#	| awk '/^\/\*.*stop editing.*\*\/$/ { print("define( \"WP_ALLOW_MULTISITE\", true );") } { print }' > temp.php \
#	&& chown --reference /usr/src/wordpress/wp-config-sample.php temp.php \
#	&& mv temp.php /usr/src/wordpress/wp-config-sample.php

RUN apt-get update

# Limpar instalação
RUN rm -rf /var/lib/apt/lists/*

# Bibliotecas php para pdo mysql
RUN docker-php-ext-install pdo_mysql

RUN yes | pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.idekey = PHPSTORM" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.default_enable = 0" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.remote_enable = 1" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.remote_autostart = 0" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.remote_connect_back = 0" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.profiler_enable = 0" >> /usr/local/etc/php/conf.d/xdebug.ini