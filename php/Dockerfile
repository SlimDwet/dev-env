FROM php:7.1-fpm

RUN echo "Modification du compte"
# On assigne le UserID 1000 a l'utilisateur www-data
RUN usermod -u 1000 www-data

# Installation de modules/packages
RUN pecl install xdebug

# Mise a jour des repos sources
RUN apt-get update && \
    apt-get install -y \
        zlib1g-dev \
        libicu-dev \
    && docker-php-ext-install \
        zip \
        intl \
        opcache \
    && docker-php-ext-enable xdebug

RUN echo "Installation de Composer"
RUN curl -s https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

RUN echo "Ajout des alias"
RUN echo "alias ll='ls -lah --color'" >> ~/.bashrc
