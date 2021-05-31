FROM php:7.4.13-fpm-alpine

ENV TIMEZONE Asia/Bangkok

RUN apk upgrade --update && apk --no-cache add \
    autoconf tzdata file g++ gcc binutils isl libatomic libc-dev \
    musl-dev make re2c libstdc++ libgcc libcurl curl-dev mpc1 gmp libgomp \
    coreutils freetype-dev libjpeg-turbo-dev libltdl libmcrypt-dev libpng-dev \
    openssl-dev libxml2-dev expat-dev oniguruma libzip-dev postgresql-dev \
    # && docker-php-ext-configure gd \
    # && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install -j$(nproc) iconv mysqli pdo_mysql pdo_pgsql curl zip opcache
# RUN docker-php-source delete
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# TimeZone
RUN cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
&& echo "${TIMEZONE}" >  /etc/timezone

# Install Composer && Assets Plugin
# RUN php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
# && composer global require --no-progress "fxp/composer-asset-plugin:~1.2" \
# && apk del tzdata \
# && rm -rf /var/cache/apk/*

EXPOSE 9000

CMD ["php-fpm"]