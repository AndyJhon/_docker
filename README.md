Install Docker

Remove old versions of docker
$ sudo apt-get remove docker docker-engine docker.io containerd runc

Update the package index
sudo apt-get update

Install packages to allow apt to use repository over https:
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
    
Add Docker’s official GPG key:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -


Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.

sudo apt-key fingerprint 0EBFCD88

Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below.

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
   
Install Docker Engine

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io

Verify 

sudo docker run hello-world


