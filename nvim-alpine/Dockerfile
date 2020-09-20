FROM alpine:latest

ENV LANG="en_US.UTF-8" LANGUAGE="en_US:ja" LC_ALL="en_US.UTF-8"

RUN apk update && \
    apk upgrade && \
    apk add --no-cache \
    build-base \
    curl \
    gcc \
    git \
    libxml2-dev \
    libxslt-dev \
    linux-headers \
    musl-dev\
    neovim \
    nodejs \
    npm \
    python2-dev \
    py-pip \
    python3-dev \
    py3-pip \
    ruby \
    ruby-dev \
    && \
    rm -rf /var/cache/apk/*

RUN pip3 install --upgrade pip
RUN pip3 install pynvim
RUN gem install -N \
    etc \
    json \
    rubocop \
    rubocop-performance \
    rubocop-rails \
    rubocop-rspec \
    solargraph

# install dein.vim
# RUN curl -sf https://raw.githubusercontent.com/Shougo/dein.vim/master/bin/installer.sh \
#     | sh -s /root/.cache/dein

COPY nvim /root/.config/nvim

# RUN nvim +:UpdateRemotePlugins +:qa
RUN chmod -R 777 /root

# ENTRYPOINT ["nvim"]
