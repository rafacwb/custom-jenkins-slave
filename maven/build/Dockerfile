FROM docker-registry-default.registry.ocp.example.com/openshift3/jenkins:v3.7

MAINTAINER Toni Syvaenen <tsyvanen@redhat.com>

ENV MAVEN_VERSION=3.3.9

USER root

# Install Skopeo
RUN yum curl -L -o /etc/yum.repos.d/devel:kubic:libcontainers:stable.repo https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/CentOS_7/devel:kubic:libcontainers:stable.repo && \
    INSTALL_PKGS="skopeo" && \
    yum -y install $INSTALL_PKGS && \
    yum clean all

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
