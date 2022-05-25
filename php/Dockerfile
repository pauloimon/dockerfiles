FROM php:cli

ARG USER_ID=1000
ARG GROUP_ID=1000
ARG USER=docker
ARG PASSWORD=secret

RUN apt-get update && \
    apt-get install -y sudo

# TODO: Install PHP extensions

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN groupadd -g ${GROUP_ID} ${USER} && \
    useradd -g ${USER} -G sudo -m -s /bin/bash -u ${USER_ID} ${USER} && \
    echo "${USER}:${PASSWORD}" | chpasswd

USER ${USER}
