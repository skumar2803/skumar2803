---
title: "Docker Fundamentals"
datePublished: Thu Jun 01 2023 17:18:44 GMT+0000 (Coordinated Universal Time)
cuid: clidehm4z000m09mn3tx5fxno
slug: docker-fundamentals
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685639815411/029f0f3f-f287-44a0-bafb-3a0387b46efb.jpeg
tags: docker, hashnodecommunity, devops-articles, devops-journey, devopscommunity

---

### <mark>Topics:</mark>

1. Docker
    
2. Docker Engine
    
3. Containers
    
4. Docker commands
    

Most of the time, the application is developed using Python 3.9, Django, and code on a windows os, but when the same application is run on a Linux machine, issue occurs like version mismatch etc. To get rid of this problem. We need to build applications In docker's virtual environments.

We use below:

1. `Docker File`
    
2. `Docker Image`
    
3. `Docker container`  
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685639165464/e97788d3-eca2-4a46-9585-eda9289e6e2c.png align="center")
    
    **<mark>Docker d (Docker Daemon)</mark> - Docker d is a service that runs in the background, to make sure images have become containers.**
    
    **What is a docker engine?**
    
    Acts on top of hyperV, it acts better than hyperV.
    
    You can run multiple containers.  
      
    *The above flowchart explains the execution flow.  
    Attribute: Self-created over one note.*  
    
    Docker is an open-source platform that allows you to automate the deployment and management of applications using containerization. A containerization is a lightweight approach to virtualization where applications are packaged together with their dependencies and isolated from the underlying infrastructure.
    

In Docker, containers are the fundamental units of software. Each container encapsulates an application and its dependencies, including the operating system, libraries, and any other required components. Containers provide consistency and portability, allowing applications to run reliably across different environments, such as development machines, testing environments, and production servers.

Docker provides tools and features that simplify the containerization process. The Docker Engine is the core component that enables the creation and execution of containers. It uses a client-server architecture, where the Docker client communicates with the Docker daemon (server) to build, run, and manage containers.

Key features of Docker include:

1. **Image-based deployment**: Docker uses images as the building blocks for containers. An image is a lightweight, standalone, and executable software package that includes everything needed to run an application.
    
2. **Containerization**: Docker isolates applications in containers, ensuring they have their file system, network interfaces, and process space. Containers are portable, allowing you to run applications consistently across different systems and environments.
    
3. **Efficiency**: Docker optimizes resource utilization by sharing the host's operating system kernel and binaries across multiple containers, reducing overhead and improving efficiency.
    
4. **Versioning and reproducibility**: Docker images can be versioned and stored in repositories, allowing for easy distribution and sharing. This enables reproducibility, ensuring that an application runs consistently regardless of the environment.
    
5. **Orchestration and scalability**: Docker can be integrated with orchestration tools like Docker Swarm and Kubernetes to manage and scale containerized applications across multiple hosts or clusters.
    

Docker has gained significant popularity due to its ability to simplify the deployment and management of applications, improve software development workflows, and enable microservices architectures. It has a large and active community, which has contributed to the creation of a vast ecosystem of Docker images and tools that extend its functionality.  

**<mark>Docker commands</mark>**<mark>:</mark>

Here are some commonly used Docker commands:

1. **docker run**: Creates and runs a new container based on an image. Example: `docker run image_name`
    
2. **docker ps**: Lists the running containers. Example: `docker ps`
    
3. **docker images**: Lists the available Docker images on your system. Example: `docker images`
    
4. **docker pull** Downloads a Docker image from a registry. Example: `docker pull image_name`
    
5. **docker stop**: Stops a running container. Example: `docker stop container_id`
    
6. **docker start**: Starts a stopped container. Example: `docker start container_id`
    
7. **docker restart**: Restarts a running container. Example: `docker restart container_id`
    
8. **docker rm**: Removes a stopped container. Example: `docker rm container_id`
    
9. **docker rmi**: Removes an image from your system. Example: `docker rmi image_name`
    
10. **docker build**: Builds a Docker image from a Dockerfile. Example: `docker build -t image_name.`
    
11. **docker exec**: Runs a command inside a running container. Example: `docker exec container_id command`
    
12. **docker logs**: Displays the logs of a container. Example: `docker logs container_id`
    
13. **docker cp**: Copies files between a container and the local filesystem. Example: `docker cp container_id:/path/to/file /local/path`
    
14. **docker network**: Manages Docker networks. Example: `docker network create network_name`
    
15. **docker-compose**: Manages multi-container Docker applications using a YAML file. Example: `docker-compose up`