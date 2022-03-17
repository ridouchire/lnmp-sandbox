FROM library/php:8.0-fpm
RUN apt update -yyq && apt install -yyq zip libzip-dev libcurl4-openssl-dev
RUN docker-php-ext-install zip
RUN docker-php-ext-install curl
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=/usr/local/bin/ --filename composer
