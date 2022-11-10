
FROM ubuntu:22.04

LABEL maintainer="Community Engineering Team <community-engg@harness.io.>"

# Change default shell for RUN from Dash to Bash
SHELL ["/bin/bash", "-exo", "pipefail", "-c"]

ENV DEBIAN_FRONTEND=noninteractive \
    TERM=dumb \
    PAGER=cat


RUN noInstallRecommends="" && \
	if [[ "22.04" == "22.04" ]]; then \
		noInstallRecommends="--no-install-recommends"; \
	fi && \
	apt-get update && apt-get install -y $noInstallRecommends \
	    elixir \
		autoconf \
		build-essential \
		ca-certificates \
		cmake \
		# already installed but here for consistency
		curl \
		gnupg \
		gzip \
		jq \
		libcurl4-openssl-dev \
		# popular DB lib - MariaDB
		libmariadb-dev \
		# allows MySQL users to use MariaDB lib
		libmariadb-dev-compat \
		# popular DB lib - PostgreSQL
		libpq-dev \
		libssl-dev \
		libsqlite3-dev \
		make \
		python3 \
		# for ssh-enabled builds
		net-tools \
		netcat \
		openssh-client \
		parallel \
		# compiling tool
		pkg-config \
		postgresql-client \
		shellcheck \
		software-properties-common \
		# already installed but here for consistency
		sudo \
		tar \
		tzdata \
		unzip \
		python3-pip \
		# for ssh-enabled builds
		vim \
		wget \
		zip && \
	add-apt-repository ppa:git-core/ppa && apt-get install -y git && \
	rm -rf /var/lib/apt/lists/*

ENV DOCKER_VERSION 5:20.10.18~3-0~ubuntu-
RUN apt-get update && apt-get install -y \
		apt-transport-https \
		ca-certificates \
		curl \
		gnupg-agent \
		software-properties-common && \
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
	add-apt-repository -y "deb [arch=$(dpkg --print-architecture)] https://download.docker.com/linux/ubuntu $( lsb_release -cs ) stable" && \
	apt-get install -y docker-ce=${DOCKER_VERSION}$( lsb_release -cs ) docker-ce-cli=${DOCKER_VERSION}$( lsb_release -cs ) containerd.io && \
	# Quick test of the Docker install
	docker --version && \
	rm -rf /var/lib/apt/lists/*

ENV COMPOSE_VER 2.11.1
ENV COMPOSE_SWITCH_VERSION 1.0.4
RUN dockerPluginDir=/usr/local/lib/docker/cli-plugins && \
	mkdir -p $dockerPluginDir && \
	curl -sSL "https://github.com/docker/compose/releases/download/v${COMPOSE_VER}/docker-compose-linux-$(uname -m)" -o $dockerPluginDir/docker-compose && \
	chmod +x $dockerPluginDir/docker-compose && \
	curl -fL "https://github.com/docker/compose-switch/releases/download/v${COMPOSE_SWITCH_VERSION}/docker-compose-linux-$(dpkg --print-architecture)" -o /usr/local/bin/compose-switch && \
		
	docker compose version && \
	chmod +x /usr/local/bin/compose-switch && \
	update-alternatives --install /usr/local/bin/docker-compose docker-compose /usr/local/bin/compose-switch 99 && \
		
	docker-compose version

RUN curl -sSL "https://github.com/mikefarah/yq/releases/download/v4.27.5/yq_linux_amd64.tar.gz" | \
	tar -xz -C /usr/local/bin && \
	mv /usr/local/bin/yq{_linux_amd64,}
