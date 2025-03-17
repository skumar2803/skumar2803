---
title: "To Enable SSH into GitHub from an EC2 instance using SSH Keys"
datePublished: Thu May 25 2023 19:10:31 GMT+0000 (Coordinated Universal Time)
cuid: cli3ieek5000g0aju9ajcf4sb
slug: to-enable-ssh-into-github-from-an-ec2-instance-using-ssh-keys
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685041720734/d228cd60-7006-4a97-889b-77eee378c2f0.png
tags: linux, devops, ssh, devops-articles, linux-commands

---

To SSH into GitHub from an EC2 instance, you need to set up SSH keys and configure your GitHub account with the public key. Here's a step-by-step guide to help you through the process:

1. Create an EC2 instance: Launch an Amazon EC2 instance if you haven't already. Make sure you have the necessary access credentials (key pair) to connect to the instance via SSH.
    
2. Connect to the EC2 instance: Use an SSH client to connect to your EC2 instance.
    
3. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685040457296/e3abe10b-9558-46cc-9cd8-663ddbb670e2.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685040343825/984c55dc-67df-40e3-9c4f-6d6827b71e01.png align="center")
    
    Execute <mark>ssh-keygen</mark> as shown above.
    
4. Add the public key to your GitHub account: After generating the SSH key pair, you need to add the public key to your GitHub account. Use the `cat` command to display the contents of the public key file (`~/.ssh/id_rsa.pub` by default) and copy the output.
    
5. cat ~/.ssh/id\_rsa.pub
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685040734138/19908013-ba67-4b3d-91d0-e1833c2a56dc.png align="center")
    
    Now in your GitHub, go to your code and select ssh and copy.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685040924155/82f34bb9-89f1-4627-a957-591b3c049d69.png align="center")
    
7. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685041015186/829ca25b-06aa-42b1-8d69-7a21ad0e9825.png align="center")
    
    GiTclone using the SSH path and you can see it is successful as shown above.
    
8. Git commit is done.
    
9. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685041216937/ddb2c19c-b823-4e41-9245-9c9555c1df65.png align="center")
    
    Using Git push to push code from local to repo (GitHub) and you can see PAT (Personal Access Token) is not required.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1685041330525/c645a721-2982-4344-a41a-3ed7a7066c9e.png align="left")