# node.js, npm and express

First of all, we should install node. To easy the process, I'm going to use docker to avoid installing everything on my local computer, by following the [NodeJS](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/) guide.

I'm going to create a simple Express application to test the deployment in the first place. The application is the following:

```
```

Here is the Dockerfile I'm going to use:

```
FROM node:12.18.1
ENV NODE_ENV=production

WORKDIR /app

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install

COPY . .

CMD [ "node", "server.js" ]

```

Now, I am able to build the Docker image and start the Docker container by doing:
```

```

To test that this actually works, lets use curl:
```
```
