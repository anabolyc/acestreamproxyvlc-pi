FROM armbuild/debian:jessie

# reqired packages
RUN apt-get update
RUN apt-get install -y unzip ca-certificates
# cleanup
RUN rm -rf /var/lib/apt/lists/*

RUN adduser --disabled-password --gecos "" tv

COPY acestream_rpi.tar.gz /tmp/acestream_rpi.tar.gz
RUN tar xfv /tmp/acestream_rpi.tar.gz -C /
RUN rm /tmp/acestream_rpi.tar.gz

EXPOSE 62062

ENTRYPOINT ["/acestream/start_acestream.sh"]
