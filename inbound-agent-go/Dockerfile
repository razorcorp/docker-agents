# syntax=docker/dockerfile:1.3-labs

FROM jenkins/inbound-agent:alpine

USER root

COPY --from=golang:alpine /usr/local/go/ /usr/local/go/
COPY --from=golang:alpine /go /go


ENV GOROOT="/usr/local/go/"
ENV GOPATH="/go"
ENV PATH="${PATH}:/go/bin:/usr/local/go/bin"

USER jenkins
