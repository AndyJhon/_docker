## To see nodes an status
<< docker node ls

## To see managers and  nodes
<< docker info | more

## Docker swarm visualizer 
Install docker swarm visualizer 
docker run -it -d -p 8080:8080 -v /var/run/docker.sock:/var/run/docker.sock dockersamples/visualizer ...

## Analyzing services with Docker

<< docker inspect

Or if you need more information 

<< man docker inspect

OK, so lets try it

<< docker service ls // to check services running and inspect

<< docker inspect service_name | more
or
<< docker inspect service_name | grep Replicas

If we need to inspect a docker container

<< docker ps // to see containers running 

<< docker inspect CONTAINER_ID | more
or for specific jason field

<< docker inspect CONTAINER_ID | grep IPAddress

## Stack and stack files

TODO



## Network ports

<< docker service update --publish-add published=8080, target=8080 service_name

then 

<< docker service inspect mystac_web | grep 8080



## Mounting volumens

<< docker service update --mount-add type=volume,source=web-vol,target=/web-vol-dir SERVICE_NAME

<< docker service inspect SERVICE_NAME | grep vol

<< docker volume ls



## Replicated vs global services

<< docker service create --mode global -- name global-service nginx

<< docker service ls

<< docker node ls




























