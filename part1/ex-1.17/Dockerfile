FROM ubuntu:18.04

ENV LC_ALL C.UTF-8
ENV LANG C.UTF-8
ENV PYENV_SHELL bash

ARG PYTHON_VERSION=3.8.3

# Install dependencies
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y -qq --no-install-recommends \
    # dependencies for pyenv install
    ca-certificates \
    curl \
    git \
    # dependencies for building python
    build-essential \
    zlib1g-dev \
    libncurses5-dev \
    libgdbm-dev \
    libnss3-dev \
    libssl-dev \
    libreadline-dev \
    libffi-dev \
    libsqlite3-dev \
    wget \
    libbz2-dev\
    # terminal experience
    zsh \
    # cleanup
    && rm -rf /var/lib/apt/lists/*

RUN git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh \
    && git clone --depth 1 git://github.com/junegunn/fzf.git ~/.fzf \
    && ~/.fzf/install --key-bindings --completion --no-update-rc --no-bash \
    && git clone --depth 1 git://github.com/zsh-users/zsh-autosuggestions.git ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions \
    && git clone --depth 1 git://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting \
    && chsh -s $(which zsh)


COPY zshrc ~/.zshrc

# Install pyenv for installing appropriate python versions
RUN curl https://pyenv.run | bash
ENV PATH /root/.pyenv/bin:/root/.pyenv/shims:${PATH}
RUN pyenv install ${PYTHON_VERSION}

ENTRYPOINT ["/bin/bash"]
