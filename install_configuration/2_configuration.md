
#See docker storage info
<< docker info | more

##Storage Drive
if you have a work load that needs persistent data in the writable layer of your container, you should look at storage drivers.

The storage drivers control how images and containers are stored on your Docker host. 

## Docker repositories and Docker Hub
A Docker repository is a collection of related Docker images with the same name but different tags. 
A registry, on the other hand, is a place where you store your images. A registry can be public, it can be private, and it can have multiple repositories 
The most common and default registry for Docker is Docker's own public registry, Docker Hub.

##Docker Hub
<< docker login
Username:
Password:

##Pull a small image
<< docker pull aplpine
and chek images
<< docker images

##Create tags to test docker hub
See docker id from images
docker tag image_id (at least 3 digits) docker_id/image_name:tag_name
<< docker tag a24 andyjhonvr/alpine:test1
<< docker tag a24 andyjhonvr/alpine:test2
<< docker tag a24 andyjhonvr/alpine:test3
and check images created
<< docker images 

##Pushing docker images
docker push docker_id/image_name
<< docker push andyjhonvr/alpine

##Validate images in Docker Hub
Go to the web site
