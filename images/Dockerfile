FROM library/php:7.2-fpm

RUN apt update -yyq && apt-get install -yyq \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        mysql-client \
        xz-utils \
        zip \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install -j$(nproc) zip \
    && docker-php-ext-install -j$(nproc) mysqli

RUN pecl install xdebug-2.6.0 && \
    echo "zend_extension=$(ls -1 /usr/local/lib/php/extensions/*/xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    pecl install Archive_Tar
