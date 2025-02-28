# Docker-For-DevOps-Crash-Course
Docker-For-DevOps-Crash-Course

Official documentation: https://docs.docker.com/

What is Docker and its benefits?

![image](https://github.com/user-attachments/assets/40b5e411-4d67-495a-a116-e1e0db3c4355)

•	Platform for developing, packaging, shipping, and running applications in an environment called container.

•	Can run many containers on a given host.

•	Containers are lightweight and have everything to run an application without relying on the host.

•	Containers can be shared and they work the same for everyone.

•	Supports CI/CD workflows.

•	Docker containers can run on a developer's local laptop, on physical or virtual machines in a data center, on cloud providers, or in a mixture of environments.

Deploying an application without Docker:

![image](https://github.com/user-attachments/assets/2332fdb1-fbca-4e07-9d9f-4feaa553c77c)

Deploying an application with Docker:

![image](https://github.com/user-attachments/assets/ad830e30-7418-4bec-af69-efa294c89da1)

Install and Configure Docker on AWS EC2 Instance with Ubuntu 24.04 LTS:

 https://docs.docker.com/engine/install/ubuntu/

Follow the below commands in sequence:

# Run the following command to uninstall all conflicting packages:

for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Set up Docker's apt repository.

# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# To install the latest docker version, run:

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Verify that the installation is successful by running the hello-world image:

sudo docker run hello-world

# Check docker service status

sudo systemctl status docker

# Add the current user (ubuntu in my case) to docker user group

sudo usermod -aG docker ubuntu

# Run jenkins as a Docker Container

docker run -d -p 8080:8080 --restart=on-failure jenkins/jenkins:lts-jdk17

# Retrieve the initial password to login to jenkins UI on http://public-ip-of-ec2-instance:8080

docker exec container-id cat /var/jenkins_home/secrets/initialAdminPassword

# Most commonly used docker commands:

Please find the PDF attached in the repo





