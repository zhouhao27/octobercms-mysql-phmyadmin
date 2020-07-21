FROM php:7.2-apache

RUN apt-get -y update --fix-missing && \
  apt-get upgrade -y && \
  # Install useful tools
  apt-get -y install --fix-missing \
    apt-utils nano wget dialog \
    fish vim \
    # Install important libraries
    build-essential git curl libcurl4 libcurl4-gnutls-dev zip openssl

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
  # Install xdebug
  pecl install xdebug-2.6.0 && \
  docker-php-ext-enable xdebug

# Other PHP7 Extensions
RUN apt-get -y install libsqlite3-dev libsqlite3-0 mysql-client zlib1g-dev && \
  docker-php-ext-install pdo_mysql \
    pdo_sqlite \
    mysqli \
    curl \
    tokenizer \
    json \
    zip

RUN apt-get -y install libicu-dev && \
  docker-php-ext-install -j$(nproc) intl && \
  docker-php-ext-install mbstring gettext  

RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN docker-php-ext-install -j$(nproc) gd

# Install vim
# ADD ./vimrc /root/.vimrc
# # 用vundle管理vim插件
# RUN git clone https://github.com/VundleVim/Vundle.vim.git /root/.vim/bundle/Vundle.vim && \
#   # 安装vim插件
#   vim -c PluginInstall -c q -c q 

# Enable apache modules
RUN a2enmod rewrite headers
