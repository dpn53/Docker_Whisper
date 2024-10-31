FROM python:3.9.9-slim

RUN apt-get update && apt-get install -y \
    bash \
    build-essential \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

##RUN useradd -ms /bin/bash vscode
USER root
WORKDIR /workspaces

## https://github.com/openai/whisper?tab=readme-ov-file