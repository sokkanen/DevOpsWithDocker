FROM ubuntu:16.04 as builder

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN apt install -y git
RUN git clone https://github.com/docker-hy/frontend-example-docker.git
WORKDIR /frontend-example-docker
RUN npm install

FROM node:8.16-alpine
COPY --from=builder /frontend-example-docker .
EXPOSE 5000 
CMD npm start
