MANDATORY EXERCISE 1.13: HELLO, BACKEND!

Create a Dockerfile for the project (example-backend). Start the container with port 8080 published.

http://localhost:8080/ping -> you should get a "pong" response.

Submit the Dockerfile and the command used


# Solution

## 1. clone project and go to example-backend

```bash
git clone https://github.com/docker-hy/material-applications

cd material-applications/example-backend
```

## 2. Create Dockerfile

```bash
FROM golang:1.24rc1-alpine3.21

WORKDIR /app

COPY . .

RUN go build
RUN go test ./...

EXPOSE 8080

CMD ["./server"]
```

## 3. Build and run

```bash
sudo docker build . -t back

sudo docker run --rm -p 8080:8080 back
```
