#
docker ps -a

#
docker ps --format $FORMAT

#
docker images

#
docker run -ti hello-world:latest

#
exit

#----------------------------------------------
#Create new image:
docker run -ti ubuntu bash

#Create a new file inside:
touch my-file-here

#
exit

#Verify las container executed
docker ps -l --to get container_id
docker commit container_id
sha256:7eaacb772f0a05e5a334f6bb2d1093a8158f875bc24fad88335c5517db30a22c

#Rename tag to image:
docker tag 7eaacb772f0a05e5a334f6bb2d1093a8158f875bc24fad88335c5517db30a22c my-image

#Check again images
docker images

#So, run image created
docker run -ti my-image bash

#Creating an image using name instead of container_id and tag command
docker commit intelligent_knuth my-new-image-bassed-on-image-name










