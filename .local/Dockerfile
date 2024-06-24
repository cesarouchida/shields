FROM centos:latest
LABEL MAINTAINER="cesarouchida"
LABEL VERSION="v3"
ENV KAFKA_VERSION=2.7.0
ENV KAFKA_BIN_VERSION=kafka_2.13-2.7.0
ENV URL_DOWNLOAD=https://downloads.apache.org/kafka/

WORKDIR kafka

COPY docker/Makefile .

RUN yum update -y
RUN yum install java make -y

RUN curl -LO $URL_DOWNLOAD$KAFKA_VERSION/$KAFKA_BIN_VERSION.tgz
RUN tar zxvf $KAFKA_BIN_VERSION.tgz
RUN mv $KAFKA_BIN_VERSION/* .

RUN rm -rf $KAFKA_BIN_VERSION.tgz
RUN rm -rf $KAFKA_BIN_VERSION/
