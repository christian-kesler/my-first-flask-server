# my-first-flask-server

Misc

If network timeouts are causing issues

sudo sysctl net.ipv4.tcp_fin_timeout=100

https://github.com/christian-kesler/my-first-python-web-server

https://github.com/christian-kesler/my-first-flask-server

Hello World with Docker Engine

https://docs.docker.com/engine/install/ubuntu

sudo apt-get update

sudo apt-get install \

ca-certificates \

curl \

gnupg \

lsb-release

sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \

"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \

$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin



https://newbedev.com/got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket-at-unix-var-run-docker-sock-post-http-2fvar-2frun-2fdocker-sock-v1-24-auth-dial-unix-var-run-docker-sock-connect-permission-denied-code-example

sudo newgrp docker

sudo chmod 666 /var/run/docker.sock

sudo usermod -aG docker ${USER}

docker login



https://stackoverflow.com/questions/61184008/unable-to-find-image-hello-worldlatest-locally

sudo docker pull hello-world

sudo docker run hello-world



Installing Git and setting up Credentials

https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-20-04

Git install

sudo apt update

sudo apt install git

git --version

Prep GitHub credentials (will store upon entering during normal operations)

git config --global user.name <username>

git config --global user.email <useremail>

git config --global credential.helper store

Pull source code

cd <chosen-path>

git init

git remote add origin <repo-url>

git pull origin main 

Generate Access token

Go to your github profile, select 

Settings 

> Developer Settings 

> Personal Access Tokens 

> Generate New Token

Give the new token repo permissions at a minimum, then click generate at the bottom

Copy the token and store it somewhere safe

Enter Github Credentials

<username>

<access_token>



Configuring and running Flask Server

Build the Image

docker build . -t <image-name>

Run the Container

docker run -it -P <image-name>

Navigate to the server url at 

172.17.0.2:5000



Podman Conversion

Installation

sudo apt update

sudo apt install podman

podman -v

Build

podman build . -t <image-name>

Run

podman run -it -p 5000:5000 <image-name>

Test

http://localhost:5000
