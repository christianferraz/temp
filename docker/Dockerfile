FROM golang:1.22 as build
WORKDIR /app
COPY . .
RUN GOOS=linux CGO_ENABLED=0 go build -ldflags="-w -s" -o cloudrun .

FROM scratch
COPY --from=build /app/cloudrun .
ENTRYPOINT ["./cloudrun"]
