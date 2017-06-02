FROM nginx

RUN echo "Ajout des alias"
RUN echo "alias ll='ls -lah --color'" >> ~/.bashrc

RUN echo "Creation du repertoire web"
RUN mkdir -p /var/www/html
RUN chown www-data:www-data /var/www/html
WORKDIR /var/www/html

RUN echo "Creation du vhost"
COPY ./local.dev.conf /etc/nginx/conf.d/

RUN echo "Modification du compte"
RUN usermod -u 1000 www-data
