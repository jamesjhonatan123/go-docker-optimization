FROM golang:1.21-alpine as builder

WORKDIR /usr/src/app

COPY . .

RUN go build -ldflags="-s -w" -v -o /usr/local/bin/app ./main.go

FROM scratch

WORKDIR /usr/src/app

COPY --from=builder /usr/local/bin/app /usr/local/bin/app

CMD [ "app" ]
