# MANGING DOCKER IMAGES

# Inspecting images

<< docker image inspect ubuntu:latetst

<< docker image inspect ubuntu:latetst | more

<< docker image inspect ubuntu:latetst | grep Os
"Os": "linux",

Or we can redirect the output

<< docker images inspect ubuntu:latest > ubuntu-inspect.txt

Then

<< nano ubuntu-inspect.txt

-- Format
<< docker image inspect ubuntu:latest --format='{{.Id}}'
Output: sha...

-- keys and values
<< docker image inspect ubuntu:latest --format='{{json .ContainerConfig}}'

<< docker image inspect ubuntu:latest --format='{{json .ContainerConfig.Hostname}}'

## Docker TAG
Create a TARGET_IMAGE that refers to SOURCE_IMAGE

<< docker image tag 692 myapp:latest 

<< docker image tag myapp:latest myapp:original

<< docker image tag ubuntu:latest andyjhonvr/ubuntu:latest


## Creating an image from a file

Building an image from a differente file that Dockerfile

Using cache by default
<< docker build -f ./dd-docker . 

Avoid using cache by default (it`s gonna take more longer to build the image)
<< docker build --no-cache=true -f ./dd-docker . 


<BP: 
Each container should only run one processor or one applicationn, that is the point of containers
Use of &&
Use of backslash \ to better organize commands
>

## Modifiying image layers

We could see many layers in the output
<< docker image history ubuntu:latest

Reduce image size and move it down to a single layer

Check if experimental: true
<< docker version 

Then, we are creating a new image 
<< docker build --squash -f dd-docker -t ubuntu:v3 .

V2 still has many layers
<< docker image history ubuntu:v2

But V3 has just one layer
<< docker image history ubuntu:v3


There is another way to reduce image size and and remove image history

<< docker container export ubuntu > ubuntu_one_layer.tar
Then
<< docker image import ubuntu_one_layer.tar
You will see an image with out tag
<< docker image ls
So, we nee to tag it
<< docker tag 123 new_ubuntu
<< docker image ls
<< docker image history new_ubuntu
Single layer in that image






