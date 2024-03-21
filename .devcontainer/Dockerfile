# Dockerfile for setting up a development container with Debian Bookworm Slim image.

# Debian Bookworm Slim docker image - https://hub.docker.com/_/debian
FROM debian:bookworm-slim

# Install required packages
RUN apt-get update 
RUN apt-get install -y locales
RUN rm -rf /var/lib/apt/lists/* 

# Set the locale
RUN localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8