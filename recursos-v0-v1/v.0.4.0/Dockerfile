FROM jenkins/jenkins:2.112
USER root
RUN apt-get update && apt-get install -y make git openjdk-8-jdk
RUN mkdir /srv/backup && chown jenkins:jenkins /srv/backup
USER jenkins
RUN echo 2.112 > /usr/share/jenkins/ref/jenkins.install.UpgradeWizard.state
RUN echo 2.112 > /usr/share/jenkins/ref/jenkins.install.InstallUtil.lastExecVersion
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
COPY --chown=jenkins:jenkins config_jenkins /var/jenkins_home

# docker build . \
#     --tag andremorita/missao-devops-jenkins:0.4.0

# docker run --name docker-jenkins-4 \
#     -d \
#     -p 8080:8080 \
#     -v jenkins_home_4:/var/jenkins_home \
#     -v jenkins_backup_4:/srv/backup \
#     andremorita/missao-devops-jenkins:0.4.0
