FROM library/php:7.3-fpm
RUN apt update -yyq && apt install -yyq libmcrypt-dev\
         xz-utils\
         zip\
         zlib1g-dev\
         libxml2-dev\
         exiftool\
         libcurl4-gnutls-dev\
         libpng-dev\
         libzip-dev\
         libjpeg62-turbo-dev\
         libfreetype6-dev
RUN docker-php-ext-install iconv
RUN docker-php-ext-install zip
RUN docker-php-ext-install soap
RUN docker-php-ext-install curl
RUN docker-php-ext-install exif
RUN docker-php-ext-install mysqli
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include --with-jpeg-dir=/usr/include
RUN docker-php-ext-install gd
RUN docker-php-ext-install sockets
RUN pecl install xdebug-2.7.0beta1
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php --install-dir=/usr/local/bin/ --filename composer
