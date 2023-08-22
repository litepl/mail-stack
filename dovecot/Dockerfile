FROM docker.io/rockylinux:8
MAINTAINER Lukasz Tylski

STOPSIGNAL SIGTERM

EXPOSE 4190/tcp 993/tcp 995/tcp 110/tcp 143/tcp

RUN dnf install -y dovecot dovecot-pgsql dovecot-pigeonhole procps-ng net-tools tcpdump && \
    dnf clean all && \
    groupadd -g 500 vmail && \
    useradd -u 500 -g 500 -d /var/spool/mail vmail

USER root

CMD ["dovecot", "-F"]
