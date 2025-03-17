---
title: "Docker installation and project React_django_demo_app"
datePublished: Sat Jun 03 2023 05:39:09 GMT+0000 (Coordinated Universal Time)
cuid: clifkdn3g000109l3h59zcenq
slug: docker-installation-and-project-reactdjangodemoapp
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685770665699/9c1d1f7b-3b72-4a57-bc32-168a96937126.png
tags: docker, docker-images, devops-articles, devops-journey

---

This blog will cover <mark>Docker installation</mark> and also a <mark>mini project about launching a </mark> **<mark>react_django_demo_app</mark>**  
To install Docker on an EC2 Ubuntu instance, you can follow these steps:

1. Connect to your EC2 instance using SSH. You can use a terminal application such as `ssh` on macOS and Linux or a tool like PuTTY on Windows.
    
2. Update the package lists for upgrades and new package installations by running the following command:
    
    ```plaintext
    sudo apt update
    ```
    
3. Install the necessary packages to allow apt to use packages over HTTPS:
    
    ```plaintext
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
    ```
    
4. Add the Docker GPG key using the following command:
    
    ```plaintext
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    ```
    
5. Add the Docker repository to the system's software repository list:
    
    ```plaintext
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```
    
6. Update the package lists again to include the Docker packages:
    
    ```plaintext
    sudo apt update
    ```
    
7. Install Docker:
    
    ```plaintext
    sudo apt install docker-ce docker-ce-cli containerd.io
    ```
    
8. Docker should now be installed. You can verify the installation by checking the Docker version:
    
    ```plaintext
    docker --version
    ```
    
9. By default, Docker requires root privileges to run. If you want to run Docker commands without using `sudo`, you can add your user to the `docker` group:
    
    ```plaintext
    sudo usermod -aG docker $USER
    ```
    
10. Log out of your SSH session and log in again to apply the group changes.
    

Now you should have Docker successfully installed on your EC2 Ubuntu instance. You can start using Docker by running Docker commands or pulling Docker images. Remember to use `sudo` or make sure your user is part of the `docker` group if you didn't use `sudo`.  
  
**<mark>Eg: Docker installation on my ubuntu</mark>**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685769019234/05e51c36-b577-4241-8e41-235e01f66bbb.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685769049852/b5fd6a2e-36e7-497c-9266-c1cd766e098f.png align="center")

**<mark>Mini Project : React_Django_Demo_App</mark>**

***Flowchart:***

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685769415328/ca22d40c-2b3b-466d-93ef-1d9487e89865.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685769674074/70492950-6abd-4b01-ba77-a37313314a87.png align="center")

`Vim Dockerfile`  
`cd react_django_demo_app`

I have deleted the dockerfile which i got from my github repo using gitclone.

`docker images`

`docker build . -t react_django_app:latest`

`docker images`

  
**Docker is run with binding port numbers of host and container port, so container is running with container ID. Now I will launch the public ip with 8000 port but need to open 8000 in host, I will go to security group and add inbound rules in EC2 instance.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685769508616/db1cd435-dd6e-45e8-a3ad-ead82a804cdd.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685769557669/1b0b5e02-2511-498b-9f72-2c29080df49f.png align="center")

`docker ps`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685770266047/791298db-2d7a-474c-b534-bf866e936f84.png align="center")

`docker run -d -p 8000:8000 react_django_app:latest`

<mark>Understanding the above command--&gt; docker run -d(detached mode) -p(bind ports) --mount source=device volume , target is the folder within the container, so both will bind and last parameter is imagename&nbsp;</mark> 

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685770030806/63b660de-f3d0-484b-90fa-f5405b87643a.png align="center")