ARG DOCKER_HUB_IMAGE_TAG=cli

FROM php:${DOCKER_HUB_IMAGE_TAG}

ARG USER_ID=1000
ARG GROUP_ID=1000
ARG USER=docker
ARG PASSWORD=secret

RUN apt-get update && \
    apt-get install -y sudo

# TODO: Install some PHP extensions here

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN groupadd -g ${GROUP_ID} ${USER} && \
    useradd -g ${USER} -G sudo -m -s /bin/bash -u ${USER_ID} ${USER} && \
    echo "${USER}:${PASSWORD}" | chpasswd

USER ${USER}
