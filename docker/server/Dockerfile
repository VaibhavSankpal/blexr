# Adding FROM clause to use the offical php apache images as a starting point
FROM php:7.1-apache

# Setting up the working directory
WORKDIR /var/www/html

# Install the defined dependencies for your project
RUN php composer.phar update \
    && php composer.phar install

# Drop all tables and completely re-build your database
RUN php artisan migrate --seed .

# Laravel requires Apache’s mod_rewrite plugin to be enabled, we can do this using the a2enmod utility
RUN a2enmod rewrite

# Copy the application code to Docker image (Copying the entire folder contents so that users can make changes to their scripts without disturbing the Dockerfile)
COPY web-app/ /var/www/html
COPY .env /var/www/html

# Entrypoint of your execution
#CMD ['']
