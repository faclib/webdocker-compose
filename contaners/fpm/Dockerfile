FROM php:fpm
MAINTAINER fobia <fobia3d@gmail.com>

RUN apt-get update && apt-get install -y \
        libmcrypt-dev \
        && apt-get install -y libpq-dev libmemcached-dev libz-dev  \
        && docker-php-ext-install -j$(nproc) mcrypt
RUN apt-get phpize

# RUN docker-php-ext-install mbstring
# RUN docker-php-ext-install exif
# RUN docker-php-ext-install opcache
RUN docker-php-ext-install ctype curl dba dom exif fileinfo filter \
    ftp gd gettext hash iconv interbase intl json mbstring mcrypt \
    opcache pcntl pdo pdo_mysql pdo_sqlite phar posix pspell readline \
    reflection session simplexml sockets spl standard \
    sysvmsg sysvsem sysvshm xml xmlreader xmlrpc xmlwriter \
    xsl zip


RUN apt-get phpize

RUN pecl install memcached && echo "extension=memcached.so" > /usr/local/etc/php/conf.d/memcached.ini
RUN pecl install xdebug && echo "extension=xdebug.so" > /usr/local/etc/php/conf.d/xdebug.ini


COPY conf/ /usr/local/etc/php-fpm.d/
CMD ["php-fpm"]






# RUN apt-get install -y \
#     php7.1-curl       \
#     php7.1-gmp        \
#     php7.1-mbstring   \
#     php7.1-phpdbg     \
#     php7.1-sqlite3    \
#     php7.1-zip        \
#     php7.1-bcmath     \
#     # php7.1-dba        \
#     # php7.1-imap       \
#     php7.1-mcrypt     \
#     # php7.1-pspell     \
#     # php7.1-sybase     \
#     # php7.1-bz2        \
#     # php7.1-dev        \
#     # php7.1-interbase  \
#     # php7.1-mysql      \
#     # php7.1-readline   \
#     # php7.1-tidy       \
#     # php7.1-cgi        \
#     # php7.1-enchant    \
#     php7.1-intl       \
#     php7.1-odbc       \
#     # php7.1-recode     \
#     php7.1-xml        \
#     php7.1-cli        \
#     php7.1-fpm        \
#     php7.1-json       \
#     php7.1-opcache    \
#     # php7.1-snmp       \
#     php7.1-xmlrpc     \
#     php7.1-common     \
#     php7.1-gd         \
#     # php7.1-ldap       \
#     # php7.1-pgsql      \
#     # php7.1-soap       \
#     php7.1-xsl        \
