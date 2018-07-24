FROM ubuntu:16.04

MAINTAINER jixinyu <848280118@qq.com>

RUN apt-get update
#install tool
RUN apt-get -y install wget
RUN apt-get -y install build-essential
RUN apt-get -y install libpcre3 libpcre3-dev openssl libssl-dev
RUN apt-get -y install libxml2-dev
RUN apt-get -y install libcurl4-gnutls-dev
ENV PHPIZE_DEPS \
		autoconf \
		dpkg-dev \
		file \
		g++ \
		gcc \
		libc-dev \
		make \
		pkg-config \
		re2c
RUN apt-get -y install $PHPIZE_DEPS
RUN apt-get update && \
        apt-get -y install vim
RUN rm -rf /var/lib/apt/lists/*
#install php
RUN wget -O php-7.0.30.tar.gz http://am1.php.net/get/php-7.0.30.tar.gz/from/this/mirror

RUN tar -xzf php-7.0.30.tar.gz && \
	 cd php-7.0.30 && \
	 ./configure --prefix=/usr/local/php \
		--with-mhash \
		--enable-ftp \
		--enable-mbstring \
		--enable-mysqlnd \
		--with-curl \
		--with-openssl \
		--with-zlib \
		#--with-snmp \
		--enable-zip \
		--enable-soap \
		--with-pdo-mysql \
		--enable-fpm && \
	make && make install

RUN useradd -ms /bin/bash www
RUN apt-get update && apt-get -y install net-tools && \
	apt-get -y install inetutils-ping && \
        apt-get -y install telnet


#EXPOSE 9000
