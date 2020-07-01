# DOCKER IMAGES

## Image 

Executable package that includes everything needed to run an application
Code, runtime, libraries, environment variables and configuration files.
Are read only
It is possible to build new images based on an image
Docker images are made of layers

## Layering with Docker images
Layer file system allows to be flexible and efficient.
Read only layers
Multiple containers are based on the same image
When an image is instatiated, or run, as a container, a top writable layer is created.
A top writable layer is deleted when the container is removed

Docker Image Union Filesystem
Manifest


## Container

Runtime instance of a image

## Docker File

Text file that contains all the commandas to build an image

ADD: copies a file into the image 
COPY: copy files into the image, preferred over ADD
VOLUME: created a mount poin as defined when the container is run
ENTRYPOINT: the executable runs when a container is run
EXPOSE: documents the ports that should be pubished
C M D: provide arguments fo the entrypoint (one allowed)
ENV: used to define environmental variables in the container
FROM: defines the base image. Must be the first instruction in Dockerfile4
RUN: 
WORKDIR: defines the working directory of the container

Example:

FROM ubuntu:18.04
COPY . /app
RUN make /app
CMD python /app/app.py

Each instruction creates one layer:

    FROM creates a layer from the ubuntu:18.04 Docker image.
    COPY adds files from your Docker client’s current directory.
    RUN builds your application with make.
    CMD specifies what command to run within the container.

Then 

<< docker build .
<< docker images ls
<< docker images inspect 123
<< docker image history 883








