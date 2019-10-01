FROM nginx:1.17.3-alpine

# Install packages
RUN apk add --no-cache rsync

# Copy backup/cleanup scripts
COPY backup /usr/local/bin/backup
COPY cleanup /usr/local/bin/cleanup
