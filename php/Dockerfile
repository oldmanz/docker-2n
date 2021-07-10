FROM php:7.4-fpm
RUN apt-get update && apt-get install --no-install-recommends -y libpq-dev \
  zlib1g-dev \
  libzip-dev \
  libfreetype6-dev \
  libjpeg62-turbo-dev \
  libpng-dev \
  acl \
  postgresql-client \
  unzip

RUN docker-php-ext-install zip \
  && docker-php-ext-configure gd --with-freetype --with-jpeg \
  && docker-php-ext-install -j$(nproc) gd \
  && docker-php-ext-install pdo pgsql pdo_pgsql \
  && docker-php-ext-install pcntl \
  && echo 'memory_limit = 256M' >> /usr/local/etc/php/conf.d/docker-php-memlimit.ini

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# CMD bash -c "cd api && ./setupApi.sh"
