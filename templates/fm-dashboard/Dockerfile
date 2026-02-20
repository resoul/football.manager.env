FROM node:24-alpine

RUN apt-get update && apt-get install -y git \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY . /app

COPY ./entrypoint.sh /tmp/entrypoint.sh
ENTRYPOINT ["sh", "/tmp/entrypoint.sh"]
