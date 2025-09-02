# Use official Python 3.12.3 slim image
FROM python:3.12.3-slim

# Avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Install required system packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        openssh-client \
        sshpass \
        git \
        curl \
        vim \
        ca-certificates \
        && rm -rf /var/lib/apt/lists/*

# Upgrade pip and install Ansible
RUN pip install --no-cache-dir --upgrade pip setuptools wheel && \
    pip install --no-cache-dir ansible

# Set working directory
WORKDIR /ansible

# Default command: show versions
CMD ["sh", "-c", "python3 --version && ansible --version"]