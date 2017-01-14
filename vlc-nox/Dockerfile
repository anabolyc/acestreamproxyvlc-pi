# Set the base image to use to armhf
FROM armbuild/debian:jessie

# reqired packages
RUN apt-get update
RUN apt-get install vlc-nox -y
# cleanup 
RUN rm -rf /var/lib/apt/lists/*

RUN adduser --disabled-password --gecos "" aceproxy

EXPOSE 4212 8011

USER aceproxy

ENV VLC_PLUGIN_PATH /usr/lib/vlc/plugins/

ENTRYPOINT ["/usr/bin/vlc"]
