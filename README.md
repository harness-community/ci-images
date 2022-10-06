## Harness CI-Image

**ci-images/base-img** is an Ubuntu Docker image created by **Harness CI Community Engineering Team** with continuous integration builds in mind. This image is designed to serve as a base image for other Harness CI Custom Images.

This image is should be useful for the users to use as a base for their own custom Docker images.

This image contains the minimum tools required to operate a build on Harness CI (such as git) as well as extremely popular and useful tools in Harness CI (such as docker).

| Languages | Link |
| --- | --- |
|CI-base Image| [Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/base-image/22.04/Dockerfile) 
|Ruby|[Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/custom-images/ruby/Dockerfile) |
|Open JDK| [Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/custom-images/openjdk/Dockerfile) |
|Node| [Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/custom-images/node/Dockerfile) 
|Rust| [Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/custom-images/rust/Dockerfile) |
|PHP| [Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/custom-images/php/Dockerfile) |
|Python| [Click Here](https://github.com/krishi0408/harness-ci-image/blob/main/custom-images/python/Dockerfile) |

### How does the base-img work
This image contains the Ubuntu Linux operating system and everything needed to run most builds on Harness CI. This includes but is not limited to:
- Git
- Docker and Docker Compose
- Dockerize
- curl, ssh etc

### Note - Rust ,PHP and Python are in progress
