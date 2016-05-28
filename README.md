# Genes Mapserver (gms)

This is basically all configuration and data needed for using a UMN
Mapserver instance to serve OGC compliant geographic data on microbes
and ocean parameters.

## Features

* Layers on Ocean Sampling Day
* Envrionmental data layers

## Note

Most of the data is stored in a remote database, which just by the
size is not easily shareable.

If you are interested please conact me @renzok

## Build

use ```gms-build``` to build the mapserver. 

## Run

### Own UMN Mapserver Installation

It should run on Mapserver 6.x (version 7 not yet tested)

### Docker Way

For fast testing on localhost 80

```
docker run \
  # daemon mode
  -d \
  # bind local port to container port 80
  -p 80:80 \
  # allow container to use host network for connecting to database 
  --net=host \
  # name of container
  --name gms \
  # mount all files needed by UMN Mapserver
  -v ${YOUR LOCAL PATH TO THIS REPOSITORY}/build:/mapserver/map \
  renzok/umn-mapserver-apache
```
