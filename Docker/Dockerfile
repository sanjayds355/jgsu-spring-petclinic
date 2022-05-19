FROM centos

MAINTAINER Chinmaya.Barik@encora.com

RUN mkdir /opt/tomcat/

WORKDIR /opt/tomcat
RUN rm -rf /opt/tomcat/*
RUN curl -O https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.63/bin/apache-tomcat-9.0.63.tar.gz
RUN tar xvzf apache-tomcat-9.0.63.tar.gz
RUN mv apache-tomcat-9.0.63 /opt/tomcat/apache-tomcat-9
RUN yum -y install java
RUN yum update -y && yum install curl -y
RUN java -version

WORKDIR /opt/tomcat/webapps
RUN curl -O -L http://13.232.246.230:8082/artifactory/artifactory-build-info/artifactory-test-job/4-1652437135564.json

EXPOSE 8080

CMD ["/opt/tomcat/bin/catalina.sh", "run"]
