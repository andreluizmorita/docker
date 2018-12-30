FROM jenkins/jenkins:2.112
USER root
RUN apt-get update && apt-get install -y make git openjdk-8-jdk
RUN mkdir /srv/backup && chown jenkins:jenkins /srv/backup
USER jenkins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

# docker run --name docker-jenkins-3 \
#     -p 8080:8080 \
#     -v jenkins_home_3:/var/jenkins_home \
#     -v jenkins_backup_3:/srv/backup \
#     andremorita/missao-devops-jenkins:0.3.0
