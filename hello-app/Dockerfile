FROM golang:1.13
ADD . /go/src/hello-app
RUN export CGO_ENABLED=0 && go install hello-app

FROM alpine:latest
COPY --from=0 /go/bin/hello-app .
ENV PORT 8080
CMD ["./hello-app"]