##
## Build
##
FROM golang:1.19 AS builder

WORKDIR /workdir

COPY ./ ./

RUN go build -o build/app app.go

##
## Run
##
FROM golang:1.19

WORKDIR /workdir

COPY --from=builder /workdir/build/ ./

EXPOSE 9080

CMD ["sh", "-c", "./app"]
