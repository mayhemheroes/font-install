# FROM fuzzers/go-fuzz:1.2.0
FROM golang:1.18 as builder

COPY . /font-install
WORKDIR /font-install

RUN go mod tidy
RUN go build

FROM debian:bookworm-slim
COPY --from=builder /font-install/font-install /