FROM debian:stretch
MAINTAINER Alin Jurj <office@perfectweb.ro>

ENV VERSION 2.0.0-rc2

RUN apt-get update && \
    apt-get install -y wget mysql-client inotify-tools procps && \
    wget https://github.com/sysown/proxysql/releases/download/v2.0.0-rc2/proxysql-rc2_2.0.0-debian9_amd64.deb && \
    dpkg -i proxysql-rc2_2.0.0-debian9_amd64.deb && \
    rm -f proxysql-rc2_2.0.0-debian9_amd64.deb && \
    rm -rf /var/lib/apt/lists/*

VOLUME /var/lib/proxysql
EXPOSE 6032 6033

COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
