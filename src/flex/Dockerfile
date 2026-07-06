FROM ubuntu:24.04 AS freedv-waveform

# Install prerequisites to allow AppImages to run
RUN apt-get update && apt-get -y install libexpat1 ca-certificates

COPY squashfs-root/ /app/

LABEL com.flexradio.waveform.name=freedv-flex
#LABEL com.flexradio.waveform.version=2.3.0

ENV APPDIR=/app
ENTRYPOINT exec /app/AppRun
