# Use Python 3.12.3 slim image
FROM python:3.12.3-slim

# Proxy build args
ARG http_proxy
ARG https_proxy

# Proxy env inside container
ENV http_proxy=${http_proxy}
ENV https_proxy=${https_proxy}
ENV no_proxy=127.0.0.1,localhost

# Install system dependencies + Ansible
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        sshpass \
        openssh-client \
        git \
        curl \
        vim \
        iputils-ping && \
    pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir ansible && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Default workdir
WORKDIR /ansible

# Default shell
CMD [ "bash" ]
