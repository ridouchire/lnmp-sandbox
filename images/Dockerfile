FROM library/php:7.3-fpm
RUN apt update -yyq && apt install -yyq libmcrypt-dev xz-utils zip zlib1g-dev libxml2-dev exiftool libcurl4-gnutls-dev libpng-dev libzip-dev
RUN docker-php-ext-install zip
RUN docker-php-ext-install soap
RUN docker-php-ext-install curl
RUN docker-php-ext-install exif
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install gd
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=/usr/local/bin/ --filename composer
