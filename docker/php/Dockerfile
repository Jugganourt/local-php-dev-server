FROM php:8.2-apache

RUN apt-get update && apt-get install -y
RUN docker-php-ext-install mysqli 
RUN docker-php-ext-install pdo 
RUN docker-php-ext-install pdo_mysql 
RUN a2enmod ssl && a2enmod rewrite

COPY ./ssl/*.pem /etc/apache2/ssl/
COPY ./apache/000-default.conf /etc/apache2/sites-available/000-default.conf

EXPOSE 80
EXPOSE 443