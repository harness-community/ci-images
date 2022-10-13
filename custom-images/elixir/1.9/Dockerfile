# vim:set ft=dockerfile:

# Do not edit individual Dockerfiles manually. Instead, please make changes to the Dockerfile.template, which will be used by the build script to generate Dockerfiles.

FROM harnesscommunity/ci-base-image:latest

LABEL maintainer="Community & CI Engineering team <community-engg@harness.io>"

SHELL ["/bin/bash", "-exo", "pipefail", "-c"]

ENV DEBIAN_FRONTEND=noninteractive \
    TERM=dumb \
    PAGER=cat

ENV ERLANG_VERSION="22.3.4"

RUN sudo apt-get update && sudo apt-get install -y --no-install-recommends \
		libodbc1 \
		libsctp1 \
		libwxgtk3.0 && \	
		erlangDEB="https://packages.erlang-solutions.com/erlang/debian/pool/esl-erlang_${ERLANG_VERSION}-1~ubuntu~bionic_amd64.deb" && \
	curl -sSL -o erlang.deb $erlangDEB && \
	sudo dpkg -i erlang.deb && \
	sudo rm -rf erlang.deb /var/lib/apt/lists/*

# Install Elixir via Erlang Solutions' .deb
ENV ELIXIR_VERSION=1.9.4
RUN elixirDEB="https://packages.erlang-solutions.com/erlang/debian/pool/elixir_${ELIXIR_VERSION}-1~ubuntu~bionic_all.deb" && \
	curl -sSL -o elixir.deb $elixirDEB && \
	sudo dpkg -i elixir.deb && \
	rm -rf elixir.deb && \
	elixir --version