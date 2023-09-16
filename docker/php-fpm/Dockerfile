ARG PHP_IMAGE_VERSION

FROM $PHP_IMAGE_VERSION

WORKDIR "/www/html/"

# Args
ARG USER_CONTAINER
ARG INSTALL_NODE
ARG NODE_VERSION
ARG INSTALL_SYMFONY_CLI
ARG GIT_USER
ARG GIT_EMAIL
ARG XDEBUG_VERSION

# Update
RUN apt-get update -y

# Add User
RUN useradd -m $USER_CONTAINER

# Install some Libs and apps
RUN apt-get install -y \ 
    nano curl wget zip unzip git gnupg \
    autoconf \
    pkg-config \ 
    libssl-dev \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    libxml2-dev \
    locales \
    jpegoptim optipng pngquant gifsicle \
    libzip-dev \
    libonig-dev \
    imagemagick \
    ca-certificates

# Install some extensions
RUN docker-php-ext-install pdo pdo_mysql mysqli gd mbstring zip exif pcntl soap
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-enable soap

# Cleanup
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Node if is required
RUN if [ "$INSTALL_NODE" = "yes" ] ; then \
        mkdir -p /etc/apt/keyrings; \
        curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key \
        | gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg; \
        echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_VERSION.x nodistro main" \
        > /etc/apt/sources.list.d/nodesource.list; \
        apt-get update -y; \
        apt-get install nodejs -y; \
        npm install --global yarn; \
    fi

# Install Symfony CLI if is required
RUN if [ "$INSTALL_SYMFONY_CLI" = "yes" ] ; then \
        curl -sS https://get.symfony.com/cli/installer | bash; \
        mv /root/.symfony5/bin/symfony /usr/local/bin/symfony; \
    fi

# Install xdebug
RUN pecl install xdebug-$XDEBUG_VERSION && docker-php-ext-enable xdebug

# Aliases
USER $USER_CONTAINER
RUN echo "alias ll='ls -lha'" >> ~/.bash_aliases

# GIT config
RUN git config --global user.name "$GIT_USER"
RUN git config --global user.email "$GIT_EMAIL"