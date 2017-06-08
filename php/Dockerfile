FROM php:7.1-fpm

RUN apt-get update
RUN echo "Ajout des alias"
RUN echo "alias ll='ls -lah --color'" >> ~/.bashrc

# Mise a jour des repos sources
RUN apt-get update

RUN echo "Installation de Composer"
RUN curl -s https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

RUN echo "Creation du repertoire web"
RUN mkdir -p /var/www/html
RUN chown www-data:www-data /var/www/html
WORKDIR /var/www/html

RUN echo "Modification du compte"
RUN usermod -u 1000 www-data