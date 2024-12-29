MANDATORY EXERCISE 1.14: ENVIRONMENT

Start both the frontend and the backend with the correct ports exposed and add ENV to Dockerfile with the necessary information from both READMEs (front, back).

Ignore the backend configurations until the frontend sends requests to _backend_url_/ping when you press the button.

You know that the configuration is ready when the button for 1.14 of frontend responds and turns green.

Do not alter the code of either project

Submit the edited Dockerfiles and commands used to run.

## 1. backend Dockerfile

```bash
FROM golang:1.24rc1-alpine3.21

WORKDIR /app

COPY . .

ENV REQUEST_ORIGIN=http://localhost:1000
EXPOSE 8080

RUN go build
RUN go test ./...

CMD ["./server"]
```

## 2. frontend Dockerfile

```bash
FROM node:16.20.2-alpine3.18

WORKDIR /app
EXPOSE 5000

COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm install
RUN npm run build
RUN npm install -g serve

CMD ["serve", "-s", "-l", "5000", "build"]
```

## 3. build and run

```bash
sudo docker build . -t backend

sudo docker build . -t frontend

sudo docker run -p 8080:8080 backend

sudo docker run -p 1000:5000 frontend
```
