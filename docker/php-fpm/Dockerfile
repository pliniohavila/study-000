FROM php:7.4-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions 
RUN apt-get update && \
    docker-php-ext-install mysqli pdo pdo_mysql mbstring exif pcntl bcmath gd && \
    docker-php-ext-enable mysqli 
    
# && \     docker-php-ext-enable mysqli

# Reinicia o PHP-FPM para aplicar as alterações
# RUN service php7.4-fpm restart

# Set working directory
WORKDIR /var/www

# pecl