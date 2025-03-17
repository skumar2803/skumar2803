---
title: "Kubernetes Basics & Architecture"
datePublished: Fri Jun 30 2023 16:47:46 GMT+0000 (Coordinated Universal Time)
cuid: cljit5hr8000008jo0cru038p
slug: kubernetes-basics-architecture
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688143622275/e894d860-579f-4b97-a99a-78e35923f2f8.png
tags: kubernetes, devops, hashnode

---

Kubernetes (K8s) is an open-source container orchestration platform designed to automate the deployment, scaling, and management of containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).

Note: The number of letters between K...........S is 8. so Kubernetes is popularly called K8s.

### The architecture of Kubernetes:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1711519468001/a98d4275-38c2-45d3-9bc2-982ab43aa594.png align="center")

**s**

Why do we use Kubernetes (K8s)?

\-Failure and downtime are mitigated.  
\-For deploying micro-services and small apps which are production ready.

\-Backup and Restores.

* Load balancing
    
* Auto healing, Health monitoring of containers and Batch execution
    

### **Components of the Control Panel**

**<mark>Kube API</mark>**: Basically for all communications. This API server directly interacts with the user and it is meant to auto scale as per load.  
**<mark>Etcd:</mark>** It stores metadata and the status of the cluster.

**<mark>Scheduler</mark>**: Whenever a user requests the creation and management of Pods.

**<mark>Controller Manager</mark>**: To ensure the actual state of the cluster matches the desired state.

### **Components of Worker Node**

**<mark>Kubelet</mark>**: The agent running on the node sends success/failure reports to the Master.

**<mark>Kube-Proxy</mark>**: Assigning IP to each POD. Since it runs on each POD, thereby each POD gets a unique IP address.

**<mark>POD</mark>**: The smallest unit in K8s. POD is a group of one or more containers that are deployed together on the same host.