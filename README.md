## Harness CI-Image

```harnesscommunity/base-image``` is an Ubuntu Docker image created by **Harness CI Community Engineering Team** with continuous integration builds in mind. This image is designed to serve as a base image for other Harness CI Custom Images.

This image is should be useful for the users to use as a base for their own custom Docker images.

This image contains the minimum tools required to operate a build on Harness CI (such as git) as well as extremely popular and useful tools in Harness CI (such as docker).

### How does the ```base-image``` Image Works

This image contains the Ubuntu Linux operating system and everything needed to run most builds on Harness Platform.

- Git
- Docker and Docker Compose
- Dockerize
- The build-essential package containing compiling tools
- jq
- curl, ssh, and much more

## Development Status

Since there are many images, they are in different stages of their life cycle. This table will show where each image is and how "ready" they are to replace their predecessor.

| Image Type | Support | Release Lifecycle | Github | Image | Image Size
| --- | --- | --- | --- | --- | --- |
| Base Image | Ubuntu (22.04) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/base-image) | [harnesscommunity/ci-base-image:latest](https://hub.docker.com/layers/harnesscommunity/ci-base-image/latest/images/sha256-7311c3cfcc7e7b3a002dde00fc2ee11494930850b79f8b88c9b7e6d63c513f04?context=repo) | 392.4 MB
| Custom Image | OpenJDK (18.0.2) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/openjdk) | [harnesscommunity/openjdk-ci-image:latest](https://hub.docker.com/repository/docker/dhrubajyotichakraborty/openjdk-ci-image) | 681.54 MB
| Custom Image | Ruby (3.1.2) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/ruby) | [harnesscommunity/ruby-ci-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/ruby-ci-image) | 659.2 MB
| Custom Image | Python (3.6) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/python) | [harnesscommunity/python-ci-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/python-ci-image) | 392.4 MB
| Custom Image | Node (18.9) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.9) | [harnesscommunity/node-ci-image:latest](https://hub.docker.com/layers/harnesscommunity/node-ci-image/latest/images/sha256-5e1c73e8662360362c4a7ea68bcb3eb1b0d23fc1146a14e92a39a6c0a5c70cef?context=repo) | 459.9 MB
| Custom Image | Node (18.6) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.6) | [harnesscommunity/node-ci-image:18.6](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.6/images/sha256-19449dff3a88bfa4de4542e871e03c73b45e0d220894c672ab147327583ca3b1?context=repo) | 415.6 MB
| Custom Image | Node (18.5) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.5) | [harnesscommunity/node-ci-image:18.5](https://hub.docker.com/layers/dhrubajyotichakraborty/node-ci-image/18.5/images/sha256-8a4d8eb6cc93b542a494f9a8959709a22581d06d29873daa689db787887a2a89?context=repo) | 415.56 MB
| Custom Image | Node (18.4) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.4) | [harnesscommunity/node-ci-image:18.4](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.4/images/sha256-32717d8dfefe6b4de7737f8beeda2ca1fa3938b3837599a93bc999ec41ab1fae?context=repo) | 372 MB
| Custom Image | Node (18.0) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.0) | [harnesscommunity/node-ci-image:18.0](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.0/images/sha256-966c87def0e3645c30e6250ffad210d4a2b72c33c75914e1414791d2461c54d3?context=repo) | 372 MB
| Custom Image | Node (17.9.1) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/17.9) | [harnesscommunity/node-ci-image:17.9.1](https://hub.docker.com/layers/harnesscommunity/node-ci-image/17.9.1/images/sha256-11ba7dde4e3a464f357cb53bfa165fd8db0fe19c667e46963f1de1440f000f43?context=repo) | 372 MB
| Custom Image | Android (2022.10) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/android/2022.10) | [harnesscommunity/android-ci-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/android-ci-image) | 2.64 GB
| Custom Image | PHP | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/php) | [harnesscommunity/php-ci-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/php-ci-image) | 654.11 MB


### How does the custom images work
1. ```harnesscommunity/ruby-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a complete Ruby version, the gem command, Bundler and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
2. ```harnesscommunity/openjdk-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a version of OpenJDK, the Java Development Kit and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
3. ```harnesscommunity/python-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a complete Python version via pyenv. pip, pipenv, and poetry are pre-installed, and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.

> Note - Rust ,PHP, Elixir and Python images are in progress

## Development

Images can be built and run locally with this repository. This has the following requirements:

- Local System of Linux (Ubuntu tested) or macOS
- Bash (v4+)
- Docker Engine (v19.03+)


## Contributor License Agreement

In order to clarify the intellectual property license granted with Contributions from any person or entity, Harness Inc. ("Harness") must have a Contributor License Agreement ("CLA") on file that has been read and followed by each contributor, indicating an agreement to the license terms [here](Contributor_License_Agreement.md). This license is for your protection as a Contributor as well as the protection of Harness; it does not change your rights to use your own Contributions for any other purpose.

## Code of Conduct

All users and contributors of the Harness community should adhere to the following [Code of Conduct](https://github.com/harness/community/blob/main/CODE_OF_CONDUCT.md)!

## Communication

Refer [Harness Community Communications Guide](https://github.com/harness-community/overview/blob/main/community_communication_guide.rst) to interact with the wider community users/contributors, join slack workgroups to get help/help other users and create topics in [community.harness.io](https://community.harness.io)

### License

Apache 2.0 License.

See [COPYING](LICENSE) for more information.


