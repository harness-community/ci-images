## Harness CI-Image

```ci-images/base-img``` is an Ubuntu Docker image created by **Harness CI Community Engineering Team** with continuous integration builds in mind. This image is designed to serve as a base image for other Harness CI Custom Images.

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
### How does the custom images work
1. ```dhrubajyotichakraborty/ruby-ci-img:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a complete Ruby version, the gem command, Bundler and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
2. ```dhrubajyotichakraborty/openjdk-ci-image:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a version of OpenJDK, the Java Development Kit and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
3. ```dhrubajyotichakraborty/python-ci-img:latest```is a Docker image created with continuous integration builds in mind. Each tag contains a complete Python version via pyenv. pip, pipenv, and poetry are pre-installed, and any binaries and tools that are required for builds to complete successfully in a Harness CI pipeline.
> Note - Rust ,PHP and Python images are in progress


## Contributor License Agreement

In order to clarify the intellectual property license granted with Contributions from any person or entity, Harness Inc. ("Harness") must have a Contributor License Agreement ("CLA") on file that has been read and followed by each contributor, indicating an agreement to the license terms [here](Contributor_License_Agreement.md). This license is for your protection as a Contributor as well as the protection of Harness; it does not change your rights to use your own Contributions for any other purpose.

## Code of Conduct

All users and contributors of the Harness community should adhere to the following [Code of Conduct](https://github.com/harness/community/blob/main/CODE_OF_CONDUCT.md)!

## Communication

Refer [Harness Community Communications Guide](https://github.com/harness-community/overview/blob/main/community_communication_guide.rst) to interact with the wider community users/contributors, join slack workgroups to get help/help other users and create topics in [community.harness.io](https://community.harness.io)

### License

Apache 2.0 License.

See [COPYING](LICENSE) for more information.


