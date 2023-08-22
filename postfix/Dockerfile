FROM docker.io/rockylinux:8
MAINTAINER Lukasz Tylski

STOPSIGNAL SIGTERM

EXPOSE 25/tcp 587/tcp

RUN dnf install -y postfix postfix-pgsql postfix-pcre \
    cyrus-sasl-lib cyrus-sasl-plain cyrus-sasl-sql cyrus-sasl-scram cyrus-sasl cyrus-sasl-md5 \
    procps-ng net-tools tcpdump && \
    dnf clean all && \
    usermod -aG tty postfix && \
    groupadd -g 500 vmail && \
    useradd -u 500 -g 500 -d /var/spool/mail vmail

USER root

CMD ["/usr/sbin/postfix", "start-fg"]
