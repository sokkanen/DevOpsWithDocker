FROM ubuntu:16.04

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt install -y nodejs && \
    apt install -y git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    apt-get remove --purge -y --auto-remove git curl && \
    rm -rf /var/lib/apt/lists/*
WORKDIR /frontend-example-docker
RUN npm install && useradd -m front && chown -R front /frontend-example-docker 
USER front
ENV API_URL=http://localhost:8000
ENTRYPOINT ["npm"]
CMD ["start"]
