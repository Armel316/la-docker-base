FROM php:8.3-fpm-alpine

# System dependencies
RUN apk add --no-cache \
    bash \
    git \
    curl \
    icu-dev \
    libzip-dev \
    zip \
    unzip

# PHP extensions required by Symfony
RUN docker-php-ext-install \
    intl \
    pdo \
    pdo_mysql \
    zip \
    opcache

# Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

# Install PHP dependencies (if extended later)
COPY composer.json composer.lock ./
RUN composer install \
    --no-dev \
    --optimize-autoloader \
    --no-interaction

# Copy application
COPY . .

# Permissions (Symfony cache & logs)
RUN chown -R www-data:www-data var

USER www-data

EXPOSE 9000
CMD ["php-fpm"]
