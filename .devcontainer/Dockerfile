ARG IMAGE

FROM ${IMAGE}

ARG DOCKER_USER
ARG DOCKER_USER_PASS
ARG TARGET_DIR

ENV DEBIAN_FRONTEND=non-interactive

# Specify packages to install
RUN apt update && \
    apt install -y \
        build-essential \
        git \
        sudo \
        vim \
        wget \
        python3 \
        cmake \
        make \
        gcc \
        gdb && \
    rm -rf /var/lib/apt/lists/*

RUN useradd --create-home --shell /bin/bash --groups sudo ${DOCKER_USER}
RUN echo "${DOCKER_USER}:${DOCKER_USER_PASS}" | chpasswd
USER ${DOCKER_USER}

RUN mkdir -p ${TARGET_DIR}
WORKDIR ${TARGET_DIR}