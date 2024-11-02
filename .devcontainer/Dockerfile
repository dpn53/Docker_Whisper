FROM python:3.9.9-slim

# Install required packages and sudo
RUN apt-get update && \
    apt-get install -y \
    bash \
    build-essential \
    curl \
    git \
    sudo \
    ffmpeg && \
    rm -rf /var/lib/apt/lists/*

# Install Whisper
RUN pip install git+https://github.com/openai/whisper.git

# Create a group and user
RUN groupadd -r vscodegroup && useradd -m -s /bin/bash -r -g vscodegroup vscode

# Set a password for the vscode user
RUN echo "vscode:vscode_81" | chpasswd

# Add vscode to the sudoers file
RUN usermod -aG sudo vscode

# Set the working directory
WORKDIR /workspaces

# Copy application files
COPY . /workspaces/

# Change ownership to the non-root user
RUN chown -R vscode:vscodegroup /workspaces

# Switch to the non-root user
USER vscode
