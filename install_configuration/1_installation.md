# INSTALLING DOCKER ON LINUX UBUNTU

## Uninstall Docker
<< sudo apt-get remove docker docker-engine docker-ce docker.io

## Update the apt package index
<< sudo apt-get update

## Allow apt to use a repository over HTTPS
<< sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

## Add Docker’s official GPG key to apt
<< curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# Verify that you now have the Docker GPG key
<< sudo apt-key fingerprint 0EBFCD88

# Add the Docker repository to apt
<< sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

# Re-Update the apt package index now that we have the Docker repositories added
<< sudo apt-get update

# Install a specific version of Docker
<< sudo apt-get install docker-ce=17.12.0~ce-0~ubuntu

# Make sure that the Docker group is already added
<< sudo groupadd docker

# Add your username to the Docker group
<< sudo usermod -aG docker $USER

# Log out and back in

# Test Docker with the version command and hello-world
<< docker version
<< docker run hello-world


# INSTALLING UNIVERSAL CONTROL PLANE
Centralized managment tool for docker enterprise infraestructure

<< docker container run --rm -it --name ucp \
  -v /var/run/docker.sock:/var/run/docker.sock \
  docker/ucp:2.2.5 install \
  --host-address <node-ip-address> \
  --interactive
  
  
  
  
