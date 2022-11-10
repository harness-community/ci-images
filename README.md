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
| Base Image | Ubuntu (22.04) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/base-image) | [harnesscommunity/ci-base-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/ci-base-image) | 392.4 MB
| Custom Image | OpenJDK (18.0.2) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/openjdk) | [harnesscommunity/openjdk-ci-image:latest](https://hub.docker.com/layers/harnesscommunity/openjdk-ci-image/18.0.2/images/sha256-41e3eba531aba28edf7c364cbcdaf4ea6f89fe1ac2cd45f1c714efbbbf9fb257?context=repo) | 703.13 MB
| Custom Image | Ruby (3.1.2) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/ruby) | [harnesscommunity/ruby-ci-image:latest](https://hub.docker.com/layers/harnesscommunity/ruby-ci-image/latest/images/sha256-b62d79b463a4d45bf56c88b61033ba94bc994632f8bbeabc1c4d1347aad10f9d?context=repo) | 680.82 MB
| Custom Image | Python (3.6) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/python) | [harnesscommunity/python-ci-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/python-ci-image) | 392.4 MB
| Custom Image | Node (18.9) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.9) | [harnesscommunity/node-ci-image:latest](https://hub.docker.com/layers/harnesscommunity/node-ci-image/latest/images/sha256-1d2d980ca593325efea6a2063219b4e93f62fb9e8cede7af0352453a1c75da92?context=repo) | 481.5 MB
| Custom Image | Node (18.6) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.6) | [harnesscommunity/node-ci-image:18.6](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.6/images/sha256-817346f56fb49e9a25e8cb579d7f9118cc78a4b3fbaf11144327ce8d240f6ef7?context=repo) | 437.18 MB
| Custom Image | Node (18.5) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.5) | [harnesscommunity/node-ci-image:18.5](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.5/images/sha256-b7fd104c7c7765b8ac529fcdd13d39ae63c5e697256b00a2c1322779e8f6bf29?context=repo) | 437.14 MB
| Custom Image | Node (18.4) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.4) | [harnesscommunity/node-ci-image:18.4](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.4/images/sha256-e622be4ff283f8b923c5682d7d38a0060f797e935aa33c62f98c50b7151640da?context=repo) | 393.59 MB
| Custom Image | Node (18.0) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/18.0) | [harnesscommunity/node-ci-image:18.0](https://hub.docker.com/layers/harnesscommunity/node-ci-image/18.0/images/sha256-9daf2db5f2a8655bd69c698c0eb97e53e905e7d3a2dba5cfa23414e9afff0a8e?context=repo) | 393.59 MB
| Custom Image | Node (17.9.1) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/node/17.9) | [harnesscommunity/node-ci-image:17.9.1](https://hub.docker.com/layers/harnesscommunity/node-ci-image/17.9/images/sha256-99f60e0d78f29d4b9275c1e97cb3ae641793b2d91b982e9a19d39c2789ee660b?context=repo) | 393.59 MB
| Custom Image | Android (2022.10) | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/android/2022.10) | [harnesscommunity/android-ci-image:latest](https://hub.docker.com/layers/harnesscommunity/android-ci-image/latest/images/sha256-ae1ea5721e8561be7ed7c70768938292c0f6ae66d8aaf46394f1c032ad7f6087?context=repo) | 2.66 GB
| Custom Image | PHP | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/php) | [harnesscommunity/php-ci-image:latest](https://hub.docker.com/repository/docker/harnesscommunity/php-ci-image) | 654.11 MB
| Custom Image | Postgres | TBU | [Click Here](https://github.com/harness-community/ci-images/tree/main/custom-images/postgres) | [harnesscommunity/postgres-ci-image:14.5](https://hub.docker.com/repository/docker/harnesscommunity/postgres-ci-image) | 738.22 MB

### How does the custom images work
1. ```harnesscommunity/ruby-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a complete Ruby version, the gem command, Bundler and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
2. ```harnesscommunity/openjdk-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a version of OpenJDK, the Java Development Kit and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
3. ```harnesscommunity/android-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains an Android environment and toolchain. Including several API SDKs, command line tools, build tools, Ant, Gradle, Google Cloud SDK, and more.


> Note - Rust ,PHP, Elixir and Python images are in progress

## Development

**Images can be built and run locally with this repository. This has the following requirements:**

- Any Linux (Ubuntu preferred) or macOS
- Docker CE (v19.03+)

**Images can also be built using the Harness CI Pipeline (Reference Pipeline)**

- Step 1: Fork the [repository](https://github.com/codewdhruv/sample-docker-image-release) & use import from git feature to fetch the ```pipelinereleasesample.yaml``` in Harness App
- Step 2: Configure the pipeline and remote repository where you are building the image
- Step 3: Create [Docker Connector](https://docs.harness.io/article/my8n93rxnw-connect-to-harness-container-image-registry-using-docker-connector) for the Docker Registry where you want to push the custom image
- Step 4: Execute the pipeline and get the custom image released

## Contributor License Agreement

In order to clarify the intellectual property license granted with Contributions from any person or entity, Harness Inc. ("Harness") must have a Contributor License Agreement ("CLA") on file that has been read and followed by each contributor, indicating an agreement to the license terms [here](Contributor_License_Agreement.md). This license is for your protection as a Contributor as well as the protection of Harness; it does not change your rights to use your own Contributions for any other purpose.

## Code of Conduct

All users and contributors of the Harness community should adhere to the following [Code of Conduct](https://github.com/harness/community/blob/main/CODE_OF_CONDUCT.md)!

## Communication

Refer [Harness Community Communications Guide](https://github.com/harness-community/overview/blob/main/community_communication_guide.rst) to interact with the wider community users/contributors, join slack workgroups to get help/help other users and create topics in [community.harness.io](https://community.harness.io)

### License

Apache 2.0 License.

See [COPYING](LICENSE) for more information.


