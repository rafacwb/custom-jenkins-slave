FROM registry.redhat.io/openshift3/jenkins-agent-maven-35-rhel7:v3.11

MAINTAINER Renato <rfelix@redhat.com>


USER root

# Install NodeJS
RUN cd /tmp && \
    curl -O https://nodejs.org/dist/v15.4.0/node-v15.4.0-linux-x64.tar.xz && \
    tar -xvf node-v15.4.0-linux-x64.tar.xz && \
    cp node-v15.4.0-linux-x64/bin/node /usr/local/bin 

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
