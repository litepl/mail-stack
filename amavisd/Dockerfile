FROM docker.io/rockylinux:8
MAINTAINER Lukasz Tylski

STOPSIGNAL SIGTERM

EXPOSE 10024/tcp 10026/tcp

RUN dnf install -y epel-release && \
    dnf install -y --enablerepo=epel,powertools amavis unrar procps-ng net-tools tcpdump && \
    dnf clean all && \
    usermod -u 995 -g 993 amavis && \
    chown -R amavis:amavis /var/run/amavisd

USER root

CMD ["amavisd", "-c", "/etc/amavisd/amavisd.conf", "foreground"]
