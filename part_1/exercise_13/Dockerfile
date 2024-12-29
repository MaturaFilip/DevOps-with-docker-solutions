FROM golang:1.24rc1-alpine3.21

WORKDIR /app

COPY . .

RUN go build
RUN go test ./...

EXPOSE 8080

CMD ["./server"]

