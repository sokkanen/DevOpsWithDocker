FROM node:8.16-alpine

RUN apk add --no-cache git && git clone https://github.com/docker-hy/frontend-example-docker.git
WORKDIR /frontend-example-docker
RUN npm install && chown -R node /frontend-example-docker
ENV FRONT_URL=http://localhost:5000
ENTRYPOINT ["npm"]
CMD ["start"]
USER node
