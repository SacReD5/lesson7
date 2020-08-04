FROM alpine

ENV TOMCAT_VERSION 9.0.37

LABEL maintainer="SacReD5"

RUN apk update\
    && apk add openjdk8-jre=8.242.08-r2 wget unzip \
    && wget -P /opt/ http://mirror.linux-ia64.org/apache/tomcat/tomcat-9/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.zip \
    && unzip /opt/apache-tomcat-$TOMCAT_VERSION.zip -d /opt/ \
    && mv /opt/apache-tomcat-$TOMCAT_VERSION/ /opt/tomcat/ \
    && chmod +x /opt/tomcat/bin/*.sh \
    && rm -rf /opt/tomcat/webapps/* \
    && rm -f /opt/apache-tomcat-$TOMCAT_VERSION.zip \
    && apk del wget unzip \
    && rm -rf /etc/apk/cache

EXPOSE 8080

CMD ["/opt/tomcat/bin/catalina.sh", "run"]
