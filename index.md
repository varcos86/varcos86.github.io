# node.js and npm

First of all, we should install node. To easy the process, I'm going to use docker to avoid installing everything on my local computer.
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

