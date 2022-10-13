# vim:set ft=dockerfile:

FROM harnesscommunity/ci-base-image:latest

LABEL maintainer="Community & CI Engineering team <community-engg@harness.io>"

ENV PYTHON_VERSION 3.10.5

RUN sudo apt-get update && sudo apt-get install -y \
		build-essential \
		ca-certificates \
		curl \
		git \
		libbz2-dev \
		liblzma-dev \
		libncurses5-dev \
		libncursesw5-dev \
		libreadline-dev \
		libffi-dev \
		libsqlite3-dev \
		libssl-dev \
		libxml2-dev \
		libxmlsec1-dev \
		llvm \
		make \
		tk-dev \
		wget \
		xz-utils \
		zlib1g-dev && \
	curl https://pyenv.run | bash && \
	sudo rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN curl https://pyenv.run | bash
RUN  pyenv install --list | grep " 3\.[678]" \
  3.6.0 \
  3.6-dev \
  3.6.1 \
  3.6.2 \
  3.6.3 \
  3.6.4 \
  3.6.5 \
  3.6.6 \
  3.6.7 \
  3.6.8 \
  3.7.0 \
  3.7-dev \
  3.7.1 \
  3.7.2 \
  3.8-dev \
pyenv install -v 3.7.2

RUN python --version && \
	pip --version && \
	# This installs pipenv at the latest version, currently 2020.6.2
	pip install pipenv wheel

# This installs version poetry at the latest version. poetry is updated about twice a month.
RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
