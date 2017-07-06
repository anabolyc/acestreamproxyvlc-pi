# Set the base image to use to armhf
FROM debian:jessie

# reqired packages
RUN apt-get update && \
 apt-get install -y git unzip python-gevent python-pip python-dev gcc && pip install psutil && apt-get remove gcc python-pip python-dev -y && \
 apt-get clean

RUN cd / && git clone https://github.com/anabolyc/aceproxy.git
# cleanup 
RUN rm -rf /var/lib/apt/lists/*
RUN apt-get remove git -y && apt-get autoremove -y

RUN adduser --disabled-password --gecos "" aceproxy

EXPOSE 8000 8081 

VOLUME /aceproxy/ 
ADD aceconfig.py /aceproxy/aceconfig.py

CMD ["/aceproxy/acehttp.py"]
