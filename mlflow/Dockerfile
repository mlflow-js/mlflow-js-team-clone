# Dockerfile
# Specify exact Node.js version for consistency
FROM node:22.7.0
WORKDIR /mlflow
# Install necessary tools
RUN apt-get update && apt-get install -y \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*
# RUN apt-get update 
# RUN apt-get install -y gcc
# RUN apt-get install -y curl
# Copy package files
# Uses package-lock.json for exact versions
COPY package*.json ./
# Install dependencies with exact versions
RUN npm ci
# Copy source code
COPY . .
# Build the project
RUN npm run build