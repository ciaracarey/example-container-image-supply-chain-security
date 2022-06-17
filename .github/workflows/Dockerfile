FROM golang:1.17-alpine as builder

RUN go install github.com/sigstore/cosign/cmd/cosign@main
RUN go install github.com/google/go-containerregistry/cmd/crane@latest

# —————

FROM golang:1.17-alpine

COPY --from=builder /go/bin/cosign /go/bin/cosign
COPY --from=builder /go/bin/crane /go/bin/crane

RUN apk add curl docker jq
RUN curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sh -s -- -b /usr/local/bin
RUN curl -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sh -s -- -b /usr/local/bin

# Install Cloudsmith CLI
RUN apk --update add python3 py3-pip python3-dev

#FROM python:3
RUN pip3 install --upgrade cloudsmith-cli
