FROM docker.io/rockylinux:8
MAINTAINER Lukasz Tylski

STOPSIGNAL SIGTERM

EXPOSE 5000/tcp

RUN dnf install -y epel-release && \
    dnf install -y clamd clamav-update procps-ng net-tools tcpdump && \
    dnf clean all

ADD clamd.conf /etc/clamd.conf

USER root

CMD ["clamd", "-c", "/etc/clamd.conf", "-F"]
