FROM golang:1.18 as builder
WORKDIR /opt/go-project
COPY . .
RUN go mod init main && go build -o testMain


FROM ubuntu:20.04
WORKDIR /opt/go-project
COPY --from=builder /opt/go-project/testMain ./testMain
CMD ["/opt/go-project/testMain"]
