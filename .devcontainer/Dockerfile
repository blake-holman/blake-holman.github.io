FROM ruby:3.0.7-bullseye

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential \
        imagemagick \
        libmagickwand-dev \
        nodejs \
        npm \
        pkg-config \
    && rm -rf /var/lib/apt/lists/*

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=1000

RUN groupadd --gid ${USER_GID} ${USERNAME} \
    && useradd --uid ${USER_UID} --gid ${USER_GID} --create-home --shell /bin/bash ${USERNAME}

ENV BUNDLE_APP_CONFIG=.bundle \
    BUNDLE_PATH=vendor/bundle

USER ${USERNAME}
