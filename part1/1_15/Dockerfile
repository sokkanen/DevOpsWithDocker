FROM ubuntu:16.04

EXPOSE 3000
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
COPY ./Unicafe /usr/unicafe
WORKDIR /usr/unicafe
RUN npm install
ENTRYPOINT ["npm"]
CMD ["start"]
