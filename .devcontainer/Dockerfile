FROM node:20.18.0

# Update package lists and install required packages
RUN apt update && apt install -y sudo gnupg2 gitinspector

# Install PNPM globally using npm to avoid Corepack signature issues
RUN npm install -g pnpm@10.4.1

# Ensure default `node` user has access to sudo
ARG USERNAME=node
RUN echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
  && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME

# Set DEVCONTAINER environment variable for orientation
ENV DEVCONTAINER=true
