FROM php:7.1-fpm

RUN echo "Modification du compte"
# On assigne le UserID 1000 a l'utilisateur www-data
RUN usermod -u 1000 www-data

# Mise a jour des repos sources
RUN apt-get update && \
    apt-get install -y \
        zlib1g-dev \
        libicu-dev \
    && docker-php-ext-install \
        zip \
        intl

RUN echo "Installation de Composer"
RUN curl -s https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

RUN echo "Ajout des alias"
RUN echo "alias ll='ls -lah --color'" >> ~/.bashrc
