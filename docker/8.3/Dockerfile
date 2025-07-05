FROM php:8.3-fpm-alpine

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN composer create-project laravel/laravel /app
WORKDIR /app
RUN /usr/bin/composer require laravel/nightwatch

CMD ["sh", "-c", "php artisan nightwatch:agent --listen-on=${NIGHTWATCH_ADDRESS:-0.0.0.0}:${NIGHTWATCH_PORT:-2407}"]

EXPOSE 2407
