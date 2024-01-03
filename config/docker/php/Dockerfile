FROM multirepo-oab.si.fr.intraorange:5002/cceip/teamtime/php-apache

ENV PHP_IDE_CONFIG = $PHP_IDE_CONFIG

ARG UID
ARG GID
ARG USERNAME

RUN chmod -R 777 /var/www/html

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

ADD php.ini /usr/local/etc/php/php.ini
ADD php-cli.ini /usr/local/etc/php/php-cli.ini

# Create the user
RUN groupadd --gid 1001 $USERNAME \
  && useradd --uid $UID --gid 1001 -m $USERNAME

USER $USERNAME
