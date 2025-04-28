FROM wordpress:latest

RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

ENV NVM_DIR=/root/.nvm
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash \
    && . "$NVM_DIR/nvm.sh" \
    && nvm install --lts \
    && nvm use --lts \
    && nvm alias default 'lts/*' \
    && node -v \
    && npm -v

ENV NODE_PATH $NVM_DIR/versions/node/v18.18.2/lib/node_modules
ENV PATH $NVM_DIR/versions/node/v18.18.2/bin:$PATH

WORKDIR /var/www/html
