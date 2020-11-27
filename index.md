# node.js and npm

First of all, we should install node. To easy the process, I'm going to use docker to avoid installing everything on my local computer, by following both [NodeJS](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/) and [Docker](https://docs.docker.com/get-started/nodejs/build-images/) guides.

Here is the Dockerfile I'm going to use to play with node:

```
FROM node:12.18.1
ENV NODE_ENV=production

WORKDIR /app

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install

COPY . .

CMD [ "node", "server.js" ]

```

