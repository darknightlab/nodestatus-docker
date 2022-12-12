FROM alpine:latest
# ARG TARGETARCH=arm64
ARG TARGETARCH
WORKDIR /
RUN apk add --no-cache tar curl gzip && \
    curl -L -o status-client_linux_${TARGETARCH}.tar.gz https://github.com/cokemine/nodestatus-client-go/releases/latest/download/status-client_linux_${TARGETARCH}.tar.gz && \
    tar -xvf status-client_linux_${TARGETARCH}.tar.gz status-client && \
    rm status-client_linux_${TARGETARCH}.tar.gz && apk del tar curl gzip
ENTRYPOINT ["/status-client"]