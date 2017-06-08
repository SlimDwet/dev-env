FROM php:7.1-fpm

RUN echo "Modification du compte"
# On assigne le UserID 1000 a l'utilisateur www-data
RUN usermod -u 1000 www-data

# Mise a jour des repos sources
RUN apt-get update

RUN echo "Installation de Composer"
RUN curl -s https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

RUN echo "Installation de l'installeur Symfony"
RUN curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony

RUN echo "Ajout des alias"
RUN echo "alias ll='ls -lah --color'" >> ~/.bashrc
