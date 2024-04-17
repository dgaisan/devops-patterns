FROM golang:1.22 AS compilerStage

WORKDIR /usr/src/app

COPY . .
RUN go build -v -o main.go .

FROM alpine:latest

WORKDIR /root

COPY --from=compilerStage /usr/src/app .
CMD ["./main"]
