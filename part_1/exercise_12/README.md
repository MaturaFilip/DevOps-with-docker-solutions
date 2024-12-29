# MANDATORY EXERCISE 1.12: HELLO, FRONTEND!


Clone, fork or download the project from https://github.com/docker-hy/material-applications/tree/main/example-frontend.

Create a Dockerfile for the project (example-frontend) and give a command so that the project runs in a Docker container with port 5000 exposed and published so when you start the container and navigate to http://localhost:5000 you will see message if you're successful.

note that the port 5000 is reserved in the more recent OSX versions (Monterey, Big Sur), so you have to use some other host port
Submit the Dockerfile.

As in other exercises, do not alter the code of the project

TIPS:

The project has install instructions in README.
Note that the app starts to accept connections when "Accepting connections at http://localhost:5000" has been printed to the screen, this takes a few seconds
You do not have to install anything new outside containers.
The project might not work with too new Node.js versions

# Solution

## 1. clone repo and go to correct folder

```bash
git clone https://github.com/docker-hy/material-applications

cd material-applications/example-frontend
```

## 2. Create Dockerfile

```bash
sudo docker search node
```

`
FROM node:16.20.2-alpine3.18

WORKDIR /app

COPY . .

RUN npm install
RUN npm run build
RUN npm install -g serve

CMD ["serve", "-s", "-l", "5000", "build"]

`

## 3. Build docker

```bash
sudo docker build -t front .
```

## 4. run the container

```bash
sudo docker run --rm -p 80:5000 front
```
