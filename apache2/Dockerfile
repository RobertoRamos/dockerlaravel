FROM ubuntu:16.04
MAINTAINER roberto.ramos.e@gmail.com
ENV DEBIAN_FRONTEND=noninteractive

#ENV GIT_NAME="Roberto Ramos"
#ENV GIT_EMAIL="roberto.ramos.e@gmail.com"


RUN apt-get update
RUN apt-get install -y software-properties-common python-software-properties
RUN LC_ALL=C.UTF-8 add-apt-repository -y -u ppa:ondrej/php
	
RUN apt-get update && apt-get install -yq --no-install-recommends \
    apt-utils \
    curl \
    # Install git
    git \
    # Install apache
    apache2 \
    # Install php 7.2
    libapache2-mod-php7.2 \
    php7.2-cli \
    php7.2-json \
	php7.2-common \
    php7.2-curl \
    php7.2-fpm \
    php7.2-gd \
	php7.2-dba \
	php7.2-bcmath \
	php7.2-bz2 \
    php7.2-ldap \
    php7.2-mbstring \
    php7.2-mysql \
    php7.2-soap \
    php7.2-sqlite3 \
    php7.2-xml \
    php7.2-zip \
    php7.2-intl \
    php-imagick \
    # Install tools
    openssl \
    nano \
    graphicsmagick \
    imagemagick \
    mysql-client \
    iputils-ping \
	ssh \
	sudo \
    locales \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set locales
RUN locale-gen en_US.UTF-8 es_ES.UTF-8

RUN a2enmod rewrite

WORKDIR /var/www/html
RUN rm index.html

# Configure user
RUN useradd -ms /bin/bash builds
RUN usermod -a -G www-data builds && usermod -a -G builds www-data
RUN chmod -R 747 /home/builds && chown -Rf builds:builds /home/builds

#USER builds
#RUN git config --global user.name GIT_NAME && git config --global user.email GIT_EMAIL

USER root
RUN chown -Rf www-data:www-data /var/www/html

VOLUME [ "/var/www/html" ]

EXPOSE 80 443

CMD ["apache2ctl", "-D", "FOREGROUND"]