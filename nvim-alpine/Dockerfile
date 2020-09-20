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
    musl-dev \
    neovim \
    nodejs \
    npm \
    ruby \
    ruby-dev \
    && \
    rm -rf /var/cache/apk/*

RUN apk add --no-cache \
    python2-dev \
    && \
    rm -rf /var/cache/apk/*
#    py-pip \
# RUN pip install --upgrade pip
RUN curl https://bootstrap.pypa.io/get-pip.py | python
RUN pip install pynvim

RUN apk add --no-cache \
    python3-dev \
    py3-pip \
    && \
    rm -rf /var/cache/apk/*
RUN pip3 install --upgrade pip
RUN pip3 install pynvim

RUN gem install -N \
    etc \
    json \
    neovim \
    rubocop \
    rubocop-performance \
    rubocop-rails \
    rubocop-rspec \
    solargraph

RUN npm install -g neovim

# install dein.vim
# RUN curl -sf https://raw.githubusercontent.com/Shougo/dein.vim/master/bin/installer.sh \
#     | sh -s /root/.cache/dein

COPY nvim /root/.config/nvim
COPY dein /root/.config/dein

# RUN nvim +:UpdateRemotePlugins +:qa
RUN chmod -R 777 /root

# ENTRYPOINT ["nvim"]
