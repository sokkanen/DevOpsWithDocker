FROM node:8.16-alpine

RUN apk add --no-cache git && git clone https://github.com/docker-hy/backend-example-docker.git
WORKDIR /backend-example-docker
RUN npm install && chown -R node /backend-example-docker
ENV FRONT_URL=http://localhost:5000
ENTRYPOINT ["npm"]
CMD ["start"]
USER node
