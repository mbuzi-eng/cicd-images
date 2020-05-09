# 1. Shared base that is independent of the service.
FROM node:latest

ENV SERVERLESS_VERSION=1.69.0
RUN npm install --global --unsafe-perm serverless@$SERVERLESS_VERSION

# Install aws cli
RUN apt-get update && apt-get install -y awscli

WORKDIR "/app"
