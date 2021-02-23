FROM golang:1.15.8-alpine3.13
WORKDIR /go/src
COPY server .
RUN go build

FROM alpine:latest  
ENV PORT=4001
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=0 /go/src/vuego-demoapp .
CMD ["./vuego-demoapp"]  
EXPOSE 4001
EXPOSE 80