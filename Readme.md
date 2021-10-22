# UniFi controller in docker

This repo contains a `Dockerfile` that builds an automatic `docker` image with
each new commit.

At each time you initialize the container it uses the actual UniFy Controller version

## TL;DR

Start up the container and mount the volume on the host.

    docker run -d -p 8443:8443 -p 8080:8080 -p 8880:8880 -v /path/to/host/volume:/usr/lib/unifi/data --name unifi joergmalter/unifi

## Settings

A default settings file will be created in your host volume in `settings.properties`.
In the container, this will be mapped to `/usr/lib/unifi/data/settings.properties`.

## Ports

To use the running UniFi instance the following ports need to be open.

* 8443 - SSL web interface (self signed)
* 8080 - Web interface
* 8880 - Guest login interface
* 3478 - UDP - STUN controller port
