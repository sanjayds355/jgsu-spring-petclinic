FROM centos

MAINTAINER Chinmaya.Barik@encora.com

RUN mkdir /opt/tomcat/

WORKDIR /opt/tomcat
RUN curl -O https://www-eu.apache.org/dist/tomcat/tomcat-8/v8.5.40/bin/apache-tomcat-8.5.40.tar.gz
RUN tar xvfz apache-tomcat-8.5.40.tar.gz
RUN mv apache-tomcat-8.5.40/* /opt/tomcat/.
RUN yum -y install java
RUN yum update -y && yum install curl -y
RUN java -version

WORKDIR /opt/tomcat/webapps
RUN curl -O -L http://13.232.246.230:8082/artifactory/artifactory-build-info/artifactory-test-job/4-1652437135564.json

EXPOSE 8080

CMD ["/opt/tomcat/bin/catalina.sh", "run"]
