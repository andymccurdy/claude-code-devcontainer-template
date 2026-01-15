FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Set `DEVCONTAINER` environment variable to help with orientation
ENV DEVCONTAINER=true

# Ensure Claude Code config has the correct permissions.
# Claude Code stores its config in both ~/.claude/ and ~/.claude.json.
# We want to persist both to a Docker named volume. However, Docker only allows named volumes to be mounted as directories.
# To get around this limitation, we can store symlink ~/.claude.json to ~/.claude/.claude.json
RUN mkdir -p /home/vscode/.claude \
  && chown -R vscode:vscode /home/vscode/.claude \
  && ln -sf /home/vscode/.claude/.claude.json /home/vscode/.claude.json

WORKDIR /workspaces/project

