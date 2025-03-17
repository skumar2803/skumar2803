---
title: "Networking Concepts"
datePublished: Mon Jun 19 2023 10:20:42 GMT+0000 (Coordinated Universal Time)
cuid: clj2phcq0000909il1fmg6k1j
slug: networking-concepts
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1687172448450/9e4fccc3-40e1-4c54-a40d-b5f0f46f4a53.jpeg
tags: hashnode, networking, devops-journey

---

[https://www.submarinecablemap.com/](https://www.submarinecablemap.com/)

Concept of ARP, RARP

Understanding HTTP methods - GET, POST, PUT and DELETE

Important Protocols, VPC creation and subnets and mapping to EC2 instance.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687170649795/37e02921-85ea-4135-a848-6a54616dc23a.png align="center")

**<mark>The OSI (Open Systems Interconnection) </mark>** model is a conceptual framework that standardizes the functions of a communication system into seven distinct layers. Each layer of the OSI model represents a specific set of tasks and protocols that facilitate communication between devices on a network.

Here are the seven layers of the OSI model, listed from the lowest layer to the highest layer:

1. Physical Layer: This layer deals with the physical transmission of raw bits over the network medium, such as electrical signals, cables, or wireless connections. It defines the specifications for the hardware and physical connections.
    
2. Data Link Layer: The data link layer provides reliable transmission of data frames between adjacent nodes on a network. It handles error detection, flow control, and synchronization. Ethernet and Wi-Fi are examples of data link layer protocols.
    
3. Network Layer: The network layer is responsible for the logical addressing and routing of data packets between different networks. It determines the optimal path for data to travel from the source to the destination using routing protocols like IP (Internet Protocol).
    
4. Transport Layer: The transport layer ensures reliable and error-free delivery of data between end systems. It provides end-to-end communication services, breaking large data chunks into smaller segments, and managing their sequencing, flow control, and error recovery. TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are transport layer protocols.
    
5. Session Layer: The session layer establishes, manages, and terminates sessions between applications. It enables two applications to establish a connection, exchange data, and close the connection once the communication is complete.
    
6. Presentation Layer: The presentation layer is responsible for data representation, translation, and encryption. It handles tasks such as data compression, encryption, and formatting, ensuring that data sent by the application layer can be understood by the receiving application.
    
7. Application Layer: The application layer is the topmost layer and is closest to the end user. It provides network services directly to user applications, enabling functions such as file transfer, email, web browsing, and remote access. Protocols like HTTP, FTP, SMTP, and DNS operate at the application layer.
    

**<mark>The TCP/IP model</mark>**, also known as the Internet Protocol Suite, is a network protocol stack that forms the basis of the modern Internet. The TCP/IP model consists of four layers, which are sometimes grouped into three functional areas.

1. Network Access Layer (or Network Interface Layer): This layer represents the lowest level of the TCP/IP model. It deals with the physical transmission of data and the protocols used to access the network medium, such as Ethernet or Wi-Fi. It handles tasks related to data links and physical layers of the OSI model.
    
2. Internet Layer: The Internet Layer is responsible for addressing, routing, and fragmenting data packets across different networks. It uses the Internet Protocol (IP) to assign unique IP addresses to devices and ensure the delivery of packets from the source to the destination. The Internet Control Message Protocol (ICMP) operates at this layer, providing diagnostic and error-reporting functionality.
    
3. Transport Layer: The Transport Layer provides end-to-end communication services between applications running on different hosts. It ensures reliable data delivery, manages data segmentation and reassembly, and handles flow control and error recovery. The most prominent protocols at this layer are the Transmission Control Protocol (TCP), which provides reliable, connection-oriented communication, and the User Datagram Protocol (UDP), which offers connectionless, unreliable communication.
    
4. Application Layer: The Application Layer is responsible for providing network services to end-user applications. It includes a wide range of protocols and services, such as HTTP (Hypertext Transfer Protocol) for web browsing, SMTP (Simple Mail Transfer Protocol) for email, FTP (File Transfer Protocol) for file transfer and DNS (Domain Name System) for domain name resolution. This layer corresponds to the application layer of the OSI model.
    

While the TCP/IP model does not strictly adhere to the seven-layer OSI model, there are similarities between the two. The Internet Layer of TCP/IP combines elements of the OSI network layer and data link layer, while the Transport Layer encompasses some functions of the OSI transport layer.  
  
[https://www.submarinecablemap.com/](https://www.submarinecablemap.com/)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687171036686/1e868214-7c8d-4b63-a1e3-01727f61c120.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687171078018/4887375a-206f-40a6-9dc4-e1aadb751f5c.png align="center")

You can view the details of cable and the companies who are associated with this. Generally, Tier 1-4 companies are involved in these as the cables are under ocean water which opens doorways for the internet to the world. They are being maintained and configured by these companies involving laying cables, to maintain the charges and bandwidth-related info and tariffs being decided like 3G, 4G as in Jio etc. In Wholesome it is a good example of collaboration.

***<mark>Why do we prefer optic cable over satellite n/w?</mark>***

***<mark>Ans: Distance via optic cable is the shortest and has less attenuation.</mark>***

The submarine cable map is a visual representation of the undersea fiber optic cables that carry the majority of international telecommunications and internet traffic between continents. These cables span across oceans and seas, connecting different countries and continents to form a global network infrastructure.

The submarine cable map displays the routes of these cables, indicating the landing points where they connect to the terrestrial networks of various countries. It provides information about the cable systems, their operators, and the capacity they provide for data transmission.

The map typically includes details such as the cable's name, owner/operator, length, and the year it became operational. It may also show additional information about the cable system's capacity, latency, and the number of fiber pairs it contains.

The submarine cable map serves as a visual reference for understanding the physical infrastructure that enables global connectivity. It highlights the interconnectivity between different regions and showcases the vital role that undersea cables play in facilitating international communication, internet access, and data transmission.

**<mark>Concept of ARP &amp; RARP</mark>**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687171501861/4f3ab60f-5438-4990-b762-e69b70f64eab.png align="center")

Let us understand this by a live example that we come across in our daily life.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687171574556/ac481542-1643-42ee-bd70-c2d612f554cb.png align="center")

Here the MAC address of the destination is unknown, henceforth the above packet is broadcasted via router across the same network and the IPAD Mac address is detected by IPAD as in our example. So it would fill in the details of the MAC address of destination and it then unicasts it to the source rather than broadcasting.  
  
**<mark>Understanding HTTP Methods with some real-time example:</mark>**

We use HTTP methods for the below:

DATA read

DATA write

DATA Update

DATA delete  
  
**HTTP methods are below:**

DATA read--- GET

DATA write--- POST

DATA Update---PUT

DATA delete----DELETE

Now let's consider IRCTC booking

 --I am checking the schedule of the train--&gt;Get

\--I am updating my details in IRCTC--&gt;POST

\--I am booking my ticket--&gt; GET & POST

\--I am deleting my account--&gt;DELETE

Protocols are a set of rules.

Eg: you want to send a file using FTP

    : you want to send mail using SMTP

**<mark>Important Protocols</mark>**

There are several important protocols in today\`s networks:

1. Internet Protocol (IP): The Internet Protocol (IP) is the core protocol of the Internet. It provides the addressing scheme and routing mechanism that enables data packets to be sent across networks.
    
2. Transmission Control Protocol (TCP): TCP is a reliable, connection-oriented protocol that ensures the orderly delivery of data packets between applications. It provides error detection, flow control, and congestion control mechanisms.
    
3. User Datagram Protocol (UDP): UDP is a connectionless, unreliable protocol that offers low overhead and faster communication compared to TCP. It is commonly used for real-time applications like streaming media, VoIP, and online gaming.
    
4. Hypertext Transfer Protocol (HTTP): HTTP is the protocol used for transferring hypertext resources, such as web pages, on the World Wide Web. It defines how web browsers and web servers communicate.
    
5. Secure Shell (SSH): SSH is a cryptographic network protocol that provides secure remote login and command execution over an insecure network. It encrypts the communication between clients and servers, offering secure remote administration.
    
6. File Transfer Protocol (FTP): FTP is used for transferring files between computers on a network. It provides a standardized way to upload, download, and manage files on remote servers.
    
7. Simple Mail Transfer Protocol (SMTP): SMTP is the primary protocol used for sending and receiving email messages. It handles the transmission and delivery of email across different mail servers.
    
8. Domain Name System (DNS): DNS is responsible for translating domain names (e.g., [www.example.com](http://www.example.com)) into IP addresses and vice versa. It enables users to access websites using human-readable domain names.
    
9. Internet Message Access Protocol (IMAP) and Post Office Protocol (POP): IMAP and POP are protocols used for retrieving email from a mail server. They allow users to access their email messages from various devices and manage them locally.
    
10. Dynamic Host Configuration Protocol (DHCP): DHCP is used to automatically assign IP addresses and network configuration parameters to devices on a network. It simplifies the process of configuring and managing network settings.
    

**<mark>VPC creation and subnets and mapping to EC2 instance</mark>**  
I am attaching a video in my LinkedIn profile with this blog on how to set up the above. However, enlisting the steps to do this.  
To create a Virtual Private Cloud (VPC) and launch an EC2 instance within it, you can follow these general steps using the AWS Management Console:

1. Log in to the AWS Management Console at [console.aws.amazon.com](http://console.aws.amazon.com).
    
2. Navigate to the Amazon VPC service.
    
3. Click on "Your VPCs" in the left sidebar and then click on "Create VPC."
    
4. Provide the necessary details for your VPC, such as a name, IPv4 CIDR block, and any optional settings. For example, you can choose to enable DNS hostname resolution and DNS support.
    
5. Click on "Create VPC" to create your VPC.
    
6. Once the VPC is created, navigate to "Subnets" in the left sidebar and click on "Create subnet."
    
7. Select your VPC, provide a name for the subnet, choose an Availability Zone, and specify the IPv4 CIDR block for the subnet.
    
8. Click on "Create subnet" to create the subnet within your VPC.
    
9. Next, navigate to "Security Groups" in the left sidebar and click on "Create security group."
    
10. Provide a name and description for the security group and specify the inbound and outbound rules to control traffic to and from the EC2 instance.
    
11. Click on "Create security group" to create the security group.
    
12. Now, go to the EC2 service by navigating to "Instances" in the left sidebar and clicking on "Launch instances."
    
13. Choose an Amazon Machine Image (AMI) for your EC2 instance.
    
14. Select the instance type, configure instance details (such as the VPC, subnet, and security group), and provide any additional settings as needed.
    
15. Review the instance details and click on "Launch" to launch the EC2 instance within your VPC.
    
16. You will be prompted to select or create an SSH key pair for secure access to the EC2 instance. Follow the instructions to proceed.
    
17. Finally, you can review the launch status and access the newly created EC2 instance within your VPC.
    

**<mark>SSH into my Ec2 instance under my custom VPC</mark>**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1687172326047/642173b6-638c-4aa4-934f-0fe2e4efe41c.png align="center")