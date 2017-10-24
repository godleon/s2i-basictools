# Ubuntu S2I builder image with basic tools
This repository is used for creating OpenShift S2I(Source to Image) builder image based on Ubuntu distribution

## Installation and Usage

This image is available on DockerHub. To pull the latest image (16.04), run:

> docker pull godleon/s2i-basictools:ubuntu16.04


To build the base image for 16.04 from scratch, run:

> git clone https://github.com/godleon/s2i-basictools.git

### Build image for Ubuntu 16.04 with stable Ansible version
> cd s2i-basictools/builds/ubuntu16.04

### Build image for Ubuntu 16.04 with latest Ansble version (installed by pip)
> cd s2i-basictools/builds/vmware-ubuntu16.04


> make build


## Test

This repository includes the S2I test framework, which launches a simple test to make sure the image builds and runs properly.

> make test