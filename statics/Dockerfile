FROM php:7.3.9-apache-buster

# Install packages
RUN apt-get update && \
    apt-get install -y rsync && \
    apt-get -y autoclean && apt-get -y autoremove && \
    apt-get -y purge $(dpkg --get-selections | grep deinstall | sed s/deinstall//g) && \
    rm -rf /var/lib/apt/lists/*

# Copy backup/cleanup scripts
COPY backup /usr/local/bin/backup
COPY cleanup /usr/local/bin/cleanup
