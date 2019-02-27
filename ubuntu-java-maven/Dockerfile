# Ubuntu 18.04 with Java 8 installed.
FROM ubuntu:18.04
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y  software-properties-common && \
    apt-get install apt-utils -y && \
    add-apt-repository ppa:webupd8team/java -y && \
    apt-get update && \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get install -y oracle-java8-installer && \
    apt-get clean && \
    cd /opt/ && \
    wget https://www-eu.apache.org/dist/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz && \
    tar -xvzf apache-maven-3.3.9-bin.tar.gz && \
    mv apache-maven-3.3.9 maven 
ENV JAVA_HOME=/usr/lib/jvm/java-8-oracle/ \
    M2_HOME=/opt/maven \
    PATH="${PATH}:${M2_HOME}/bin"
