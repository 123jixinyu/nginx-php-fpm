FROM ubuntu:16.04

MAINTAINER jixinyu <848280118@qq.com>


RUN apt-get update && \
	#install wget tool
	apt-get -y install wget && \
	#install gcc compiler
	apt-get -y install build-essential && \
	apt-get -y install libpcre3 libpcre3-dev openssl libssl-dev && \
	#install nginx
 	mkdir app && \
	wget http://nginx.org/download/nginx-1.15.1.tar.gz && \
	tar -xzf nginx-1.15.1.tar.gz && \
	cd nginx-1.15.1 && \
	./configure --prefix=/usr/local/nginx && \
	make && make install && \
	#delete app after install 
	rm -rf /var/lib/apt/lists/*

RUN apt-get update && \
	apt-get -y install vim && \
	apt-get -y install net-tools && \
	apt-get -y install inetutils-ping && \
	apt-get -y install telnet
EXPOSE 80
