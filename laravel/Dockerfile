FROM bitnami/laravel:latest

# Install required packages including bash
RUN apt-get update && apt-get install -y \
    bash \
    curl \
    git \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Install NVM and Node
ENV NVM_DIR=/root/.nvm
RUN bash -c " \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash && \
    source $NVM_DIR/nvm.sh && \
    nvm install --lts && \
    nvm use --lts && \
    nvm alias default 'lts/*' && \
    node -v && \
    npm -v \
"

# Expose the port
EXPOSE 80
