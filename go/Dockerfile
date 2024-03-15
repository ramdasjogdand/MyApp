# Start from the official Golang image
FROM golang:1.17-alpine as builder

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build -o myapp .

FROM alpine:latest  

WORKDIR /root/

COPY --from=builder /app/myapp .

CMD ["./myapp"]
