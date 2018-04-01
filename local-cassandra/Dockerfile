#FROM alpine:latest
FROM openjdk:8u121-jre-alpine 

MAINTAINER Kemal BAYINDIR <kemalbayindir@gmail.com>


RUN apk add --no-cache curl
RUN apk add --no-cache wget
RUN apk add --no-cache tar
RUN apk add --no-cache gzip

EXPOSE 9042:9042

RUN rm -rf /etc/cassandra
RUN mkdir /etc/cassandra

RUN wget http://ftp.itu.edu.tr/Mirror/Apache/cassandra/3.11.2/apache-cassandra-3.11.2-bin.tar.gz
RUN mv apache-cassandra-3.11.2-bin.tar.gz /etc/cassandra/apache-cassandra-3.11.2-bin.tar.gz

RUN cd /etc/cassandra
WORKDIR /etc/cassandra
RUN tar -xvzf apache-cassandra-3.11.2-bin.tar.gz
RUN rm -rf apache-cassandra-3.11.2-bin.tar.gz
RUN ls -al
RUN /bin/sh /etc/cassandra/apache-cassandra-3.11.2/bin/cassandra -R
