FROM alpine

LABEL maintainer="SacReD5"

RUN apk update\
    && apk add openjdk8=8.242.08-r2 git maven \
    && mkdir /opt/project \
    && git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /opt/project \
    && mvn -f /opt/project/pom.xml clean package \
    && mkdir /opt/application \
    && cp /opt/project/target/hello-1.0.war /opt/application/ \
    && rm -rf /opt/project \
    && apk del git maven \
    && rm -rf /etc/apk/cache
