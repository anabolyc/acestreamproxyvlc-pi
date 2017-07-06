FROM ubuntu:14.04

# reqired packages

RUN apt-get update -y && \
 apt-get install -y wget ca-certificates python-minimal python-setuptools

RUN echo 'deb http://repo.acestream.org/ubuntu/ trusty main' > /etc/apt/sources.list.d/acestream.list && \
 wget -q -O - http://repo.acestream.org/keys/acestream.public.key | apt-key add - && \
 apt-get update -y && \
 apt-get install -y acestream-engine && \
 apt-get clean

# cleanup
RUN rm -rf /var/lib/apt/lists/*

RUN adduser --disabled-password --gecos "" tv

EXPOSE 62062
# 6878 8621

ENTRYPOINT ["/usr/bin/acestreamengine"]

CMD ["--client-console", "--live-buffer", "50", "--max-connections", "1000", "--max-peers", "500"]
