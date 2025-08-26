FROM golang:1.24.2-bullseye

# Install Node.js (for frontend)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs

#Install Postgres client
RUN apt-get update && apt-get install -y postgresql-client

#Install Redis client
RUN apt-get update && apt-get install -y redis-tools

#Install SSH client for git
RUN apt-get update && apt-get install -y openssh-client

# Set up workspace
WORKDIR /workspace