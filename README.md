# DEPRECATED

Please visit https://github.com/ayudadigital/gp-nginx

# Generic Platform - Nginx Statics Server

## Overview

Docker image and docker-compose sample configuration to bring up a Nginx Statics Server Product to the Teecke [Docker Generic Platform (GP)](https://github.com/ayudadigital/docker-generic-platform).

## Configuration

The product is formed by one container:

- **statics**: based on [nginx:1.17.8](https://hub.docker.com/_/nginx?tab=tags&page=1&name=1.17.8-alpine) alpine docker image.

## Operation

1. Use the `docker-compose.yml.sample` file as your docker-compose configuration file.

2. Install assets with `devcontrol assets-install` and copy your static files in the `data/usr/share/nginx/html` directory.

3. Start with `docker-compose up -d`.

4. Open the url <http://localhost:8090> in a browser to view your statics.

5. Manage backups of your files:

   1. Make a backup executing `docker-compose exec statics backup`.
   2. Find the current backup within the `/var/backups/gp/statics/` of the container.
   3. Extract the current backup executing `docker cp $(docker-compose ps -q statics):/var/backups/gp gp`.

6. Stop the platform with `docker-compose stop`.

You can use this docker piece with the [Docker Generic Platform](https://github.com/ayudadigital/docker-generic-platform) project.

## Known issues

None known
