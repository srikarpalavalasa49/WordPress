# Set the base image
FROM php:7.4-apache

# Set ARG variables for WordPress installation
ARG DB_HOST
ARG DB_NAME
ARG DB_USER
ARG DB_PASSWORD

# Set the working directory within the container
WORKDIR /var/www/html

# Copy the WordPress files to the container
COPY . .

# Install necessary dependencies
RUN apt-get update \
    && apt-get install -y \
        libpng-dev \
        libjpeg-dev \
        libonig-dev \
        libxml2-dev \
        zip \
        unzip \
    && docker-php-ext-install -j$(nproc) \
        gd \
        mbstring \
        mysqli \
        opcache \
        pdo \
        pdo_mysql \
        xml \
    && a2enmod rewrite

# Set up Apache configuration
COPY apache-config.conf /etc/apache2/sites-available/000-default.conf

# Set up environment variables for WordPress installation
ENV WORDPRESS_DB_HOST=$DB_HOST \
    WORDPRESS_DB_NAME=$DB_NAME \
    WORDPRESS_DB_USER=$DB_USER \
    WORDPRESS_DB_PASSWORD=$DB_PASSWORD

# Set the entrypoint and command to start Apache
ENTRYPOINT ["apache2ctl"]
CMD ["-D", "FOREGROUND"]
