FROM jenkins/jenkins:latest

Maintainer "Edi Guy"

ENV JAVA_OPTS="-Xmx8192m"
ENV JENKINS_HOME /var/jenkins_home

# Jenkins home directory is a volume, so configuration and build history 
# can be persisted and survive image upgrades
VOLUME /var/jenkins_home

ENV NAME=jenkins

ENV JENKINS_LOG=/var/log/$NAME/$NAME.log

EXPOSE 80

