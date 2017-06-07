FROM alpine

RUN apk update && apk add flite

# add app binary from `make build` to /app
ADD app /app
ENTRYPOINT ["/app"]