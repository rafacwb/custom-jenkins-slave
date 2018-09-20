FROM docker-registry-default.registry.ocp.example.com/openshift3/jenkins:v3.7

MAINTAINER Toni Syvaenen <tsyvanen@redhat.com>

ENV MAVEN_VERSION=3.3.9

USER root

# Install Skopeo
RUN yum repolist > /dev/null && \
    yum clean all && \
    INSTALL_PKGS="skopeo" && \
    yum install -y --enablerepo=rhel-7-server-extras-rpms --setopt=tsflags=nodocs $INSTALL_PKGS && \
    rpm -V $INSTALL_PKGS && \
    yum clean all

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
