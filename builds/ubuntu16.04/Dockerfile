# This image is an Ubuntu base image for Source-to-Image builds
FROM williamyeh/ansible:ubuntu16.04
MAINTAINER godleon <godleon@gmail.com>

LABEL \
    io.k8s.description="Ubuntu 16.04 with Common Utilities" \
    io.k8s.display-name="Ubuntu 16.04 builder image" \
    io.openshift.tags="builder,ubuntu,xenial" \
    # Location of the STI scripts inside the image.
    io.openshift.s2i.scripts-url="image:///usr/libexec/s2i"

ENV \
    # Path to be used in other layers to place s2i scripts into
    STI_SCRIPTS_PATH=/usr/libexec/s2i \
    # The $HOME is not set by default, but some applications needs this variable
    HOME=/opt/app-root/src \
    PATH=/opt/app-root/src/bin:/opt/app-root/bin:$PATH

RUN INSTALL_PKGS="git \
make \
curl" && \
export DEBIAN_FRONTEND=noninteractive && \
apt-get -yq update && \
apt-get -yq install $INSTALL_PKGS && \
apt-get clean && \
git clone https://github.com/godleon/s2i-basictools.git && \
cd s2i-basictools &&

ENV PLAYBOOK s2i-basictools/setup.yml
RUN ansible-playbook-wrapper -vvv