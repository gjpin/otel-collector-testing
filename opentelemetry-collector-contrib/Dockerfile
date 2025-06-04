FROM debian:stable-slim

RUN apt update && apt install -y curl tar

RUN curl --proto '=https' --tlsv1.2 -fOL https://github.com/open-telemetry/opentelemetry-collector-releases/releases/download/v0.127.0/otelcol-contrib_0.127.0_linux_arm64.tar.gz
RUN tar -xvf otelcol-contrib_0.127.0_linux_arm64.tar.gz

ARG USER_UID=10001
ARG USER_GID=10001
USER ${USER_UID}:${USER_GID}

EXPOSE 4317 55680 55679
ENTRYPOINT ["/otelcol-contrib"]