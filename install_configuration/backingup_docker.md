# BACKING UP DOCKER


# Docker swarm cluster
<< systemctl stop docker
<< cd /var/lib/docker
Copy and archive the swarm directory
<< systemctl start docker

# Universal Control Plane (UCP)


# Docker Trusted Registry

# Container Volume Data
Should not be in your container
Best practice is to keep it in a container volume
Container volumen could be stored in Docker nodes or public cloud

