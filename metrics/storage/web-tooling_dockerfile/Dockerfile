# Copyright (c) 2020 Intel Corporation
#
# SPDX-License-Identifier: Apache-2.0

# Set up an Ubuntu image with 'web tooling' installed

# Usage: FROM [image name]
FROM ubuntu:latest

# Version of the Dockerfile
LABEL DOCKERFILE_VERSION="1.0"

# URL for web tooling test
ENV WEB_TOOLING_URL "https://github.com/v8/web-tooling-benchmark"
ENV NODEJS_URL "https://deb.nodesource.com/setup_14.x"
ENV NODEJS_VERSION "setup_14.x"

RUN apt-get update && \
	apt-get install -y build-essential git curl sudo && \
	apt-get remove -y unattended-upgrades && \
	curl -OkL https://deb.nodesource.com/${NODEJS_VERSION} && chmod +x ${NODEJS_VERSION} && ./${NODEJS_VERSION} && \
	apt-get install -y nodejs && \
	git clone ${WEB_TOOLING_URL} && \
	cd /web-tooling-benchmark/ && npm install --unsafe-perm

CMD ["/bin/bash"]
