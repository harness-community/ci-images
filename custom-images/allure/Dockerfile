# vim:set ft=dockerfile:

# Do not edit individual Dockerfiles manually. Instead, please make changes to the Dockerfile.template, which will be used by the build script to generate Dockerfiles.

FROM harnesscommunity/ci-base-image:latest

LABEL maintainer="Harness Community Engineering <community-engineering@harness.io>"

ENV JAVA_VERSION 21.0.4
ENV ALLURE_VERSION=2.30.0
ENV PATH=/opt/allure/bin:$PATH
ENV JAVA_HOME /usr/local/jdk-${JAVA_VERSION}

ENV JDK_DOWNLOAD_URL https://github.com/adoptium/temurin21-binaries/releases/download/jdk-21.0.4%2B7/OpenJDK21U-jdk_x64_linux_hotspot_21.0.4_7.tar.gz
ENV ALLURE_DOWNLOAD_URL https://repo.maven.apache.org/maven2/io/qameta/allure/allure-commandline/${ALLURE_VERSION}/allure-commandline-${ALLURE_VERSION}.zip

## DOWNLOAD AND INSTALL JAVA JDK
RUN curl -sSL -o java.tar.gz "${JDK_DOWNLOAD_URL}" && \
	sudo mkdir /usr/local/jdk-${JAVA_VERSION} && \
	sudo tar -xzf java.tar.gz --strip-components=1 -C /usr/local/jdk-${JAVA_VERSION} && \
	rm java.tar.gz && \
	sudo ln -s /usr/local/jdk-${JAVA_VERSION}/bin/java /usr/bin/java && \
	sudo ln -s /usr/local/jdk-${JAVA_VERSION}/bin/javac /usr/bin/javac && \
	sudo ln -s /usr/local/jdk-${JAVA_VERSION}/bin/javaws /usr/bin/javaws && \
	# Install packages to help with legacy image migration
	sudo apt-get update && sudo apt-get install -y \
		fontconfig \
	&& \
	sudo rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
	# The dual version command is to support OpenJDK 8
	java --version || java -version && \
	javac --version || javac -version

## DOWNLOAD AND INSTALL ALLURE REPORT CLI
RUN curl -sSL --fail --retry 3 "$ALLURE_DOWNLOAD_URL" -o allure-commandline.tar.gz && \
	sudo unzip allure-commandline.tar.gz -d /opt/ && \
	rm allure-commandline.tar.gz && \
	sudo ln -s /opt/allure-* /opt/allure && \
	allure --version
