FROM golang:1.22 AS build

WORKDIR /app 

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM alpine:latest
WORKDIR /app

COPY --from=build /app/app .

RUN ls -ltah .

CMD ["./app"]
