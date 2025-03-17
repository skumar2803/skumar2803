---
title: "AWS Migration from On Premise to Aws cloud"
datePublished: Wed Mar 20 2024 11:10:55 GMT+0000 (Coordinated Universal Time)
cuid: cltzpd6ue000008jr81ay7s1c
slug: aws-migration-from-on-premise-to-aws-cloud
tags: aws, migration, aws-migration-services

---

![How to migrate on-premises workloads with AWS Application Migration Service  | AWS Public Sector Blog](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/07/08/migrating-cms-on-premise-workload-aws-mgn-figure-1.png align="left")

* **Steps**:
    
    1. Preparation
        
    2. Planning
        
    3. Migrate
        
    4. Monitor
        
    5. Optimize
        
    
     **<mark>7 R`s- AWS Cloud Migration Strategies</mark>**
    
    `Rehost mechanism` **- Basically lift &shift strategy. Moving the services from on prem(private cloud) to Aws cloud (public cloud)with same os types and independent of h/w, platform independent. Eg:vpshere to aws**
    
    `Replatform mechanism`**\- Here once you move from on prem to aws cloud, you take advantage of aws platform services eg: containerisation, scalablity, HA.**
    
    `Refactor/Rearchitecture model` **- Suitable in monolithic application when migrated, we have to rearchitecture your application to move into microservices, so you will choose best approach eg: security, scalability and HA.**`Repurchase` **-  Very less used these days. Lets say you use vmware on premises, when you move into aws or you look for same kind of platform.**
    
    `Relocate` **- Consider you have K8 cluster running on prem. You will move to EKS or openshift on AWS (popularly called as ROSA). It is costly and you are changing the platform as well. So need to be extra cautious while using this strategy.**
    
    `Retire` **- Out of 100 applications, you see 10 application no user is using them. So you retire them rather than migrating.**
    
    `Retain` **- Consider some services or application which you have and they are secured and the organisation doesn’t want to migrate that to aws. Other services will be henceforth  migrated to aws and there will be a secure gateway to connect them over on prem. This type of strategy is called as Retain mechanism.**
    
     ***<mark>Preparation &amp; Planning</mark>***  <mark>&nbsp; (One time activity)</mark>\--It is a part of cloud migration strategy. Consider a example with an organization with 200 microservices and single monolithic application.  
    Now organization wants the monolithic application transform to microservice architecture. This is the preparation stage and you will consider the current architecture of your application. When you want the application to move into cloud native nature, we look out for microservices especially containers or orchestration platform.  
      
    While in the ***<mark>planning stage</mark>***, you will decide:
    
     -- which services have to go into beginning phases. That is splitting 200 services into 5 phases. Eg: phases can be 1,2….  
        So the critical ones will be at the last stage eg: phase 5
    
        the less critical ones will be at the beginning phase eg: phase 1
    
    ***<mark>Migration &amp; Monitor</mark>\--*** Migration can be in multiple phases. Migrate phase may have TF scripts for creating ec2 instances or cron jobs or cloudwatch logs. Once the migration is done and you will monitor the application for a while depending on the criticality. Testing team may create testautomation script to run once in a day as an example. So we can create a dashboard or check the performance on the monitoring tool to review them.
    
    ***<mark>Optimize</mark>*** \--  Once the migration is done, we evaluate what did we achieve ? -- cost benefit, overall maintenance cost is lowered, performance improvement has happened post migration. If the cost optimization is 40 % , can we optimize to 50% and we can create JIRA or task for improvement.
    
* ### **<mark>When your applications are linked to databases</mark>**
    
    \-Take backup of databases
    
    \-Find a right fit that is using aws RDS eg from mssql to Nosql
    
    \- Incase of any uncalled situation, you will simply point the databases to the on prem environment.
    
* ### <mark>How to configure the MGN (Application Migration service) and setting up the templates (Replication, Launch template..) in AWS console.</mark>
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932169021/b7a31ac2-7425-44fd-8e86-6ce2d60961f5.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932193166/4d3dd510-aec9-4f33-bed6-5c53a6e4a25a.png align="center")
    
    Once you initialize MGN, there are 7 roles created.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932255731/7e9bc208-dc19-45a6-95f9-63602308e8e8.png align="center")
    
    You will see 3 templates here:  
      
    <mark>Replication Template</mark>
    
    <mark>Launch Template</mark>  
    <mark>Post launch Template</mark>
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932331602/5a662af1-ac18-499b-8a70-abd81ce4a6e2.png align="center")
    
    So you may edit the parameters here in the templates based on your requirement as in ec2 instance type, EBS volume type as in gp3 or gp2.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932370335/ec667d6e-05a9-4c2b-9f92-857e1f864b07.png align="center")
    
    \-You may follow the below article for installing aws replication agent onto your on premises box(depending on the OS)
    
    [https://docs.aws.amazon.com/drs/latest/userguide/agent-installation.html](https://docs.aws.amazon.com/drs/latest/userguide/agent-installation.html)
    
    Next step create a User<mark>(MGNuser)</mark> in <mark> IAM (with least privilege) as service account</mark>
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932413798/cf789ab1-c88a-4923-bda1-0226fa241310.png align="center")
    
    Now  set policy to [AWSApplicationMigrationAgentPolicy](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/policies/details/arn%3Aaws%3Aiam%3A%3Aaws%3Apolicy%2FAWSApplicationMigrationAgentPolicy) as below
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932465330/97ee4f47-6dbd-49d7-9008-9c751c570bdc.png align="center")
    
    **<mark>Create the access key here</mark>**:
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932499158/2a6f32b3-a234-407d-a41a-43d2ec3abb90.png align="center")
    
    Once the above process are completed and the servers have been configured with replication agent.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932533496/47e49bb7-0aae-4ad8-b4d9-de42c2f88628.png align="center")
    
    Here you will find the below parameters:  
    1- <mark>Replication progress</mark>
    
    2-<mark>Elapsed replication time</mark>
    
    3-<mark>Total replicated storage</mark>
    
    4-<mark>Replication type – Agent bases or Agentless</mark>
    
* From here we can have <mark>POC(proof of concepts)</mark>, decides how much downtime we need to set for the entire process of migration.
    
* POC is determined by time taken during pilot migration , N/w bandwidth etc.
    
* As stated above: we have 6 stages or lifecycles:
    
*   
    1-<mark>Not Ready</mark>\- The server is undergoing sync process and is not ready for testing.
    
    2-<mark>Ready for Testing</mark>\-The server has been successfully added to MGN (Application migration service). Sync is done.
    
    3-<mark>Test in progress</mark> – The test instance is embarked currently.
    
    4-<mark>Ready for cutover</mark>\-The server has been reviewed and tested and is ready for the cutover to begin.
    
    5-<mark>Cutover in progress</mark> – A cutover instance is launched currently.
    
    6-<mark>Cutover complete</mark>\-The cutover has completed and all the data of this server has been migrated to the new launched cutover instance.
    
    Under source server-check for test and cutover
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932610331/b4ccb9ee-47d0-436f-aaa6-ea283525f2f1.png align="center")
    
    Only when the launch test instance and mark as ready for cutover is done, we will be able to launch the cutover as below.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1710932643223/2e16f69e-af8d-409f-9f7f-dc43a91ca4b1.png align="center")
    

### Summary of all the steps:

* 1- Initialising the MGN and setting up roles in IAM
    
* 2- Create a IAM service account with privileges (AWSApplicationMigrationAgentPolicy)
    
* 3- Do a system review from past using tools like New relic etc.
    
* 4- Installing the replication agent on the on Prem servers which will undergo migration.
    
* 5- Review the replication status
    
* 6- Review the launch template and then launch the test instance.
    
* 7- Verify the health of test instances
    
* 8- Mark ready for cutover
    
* 9- Power down source server
    
* 10- Launch cutover instance.
    
* 11- Review the cutover instance.
    
* 12- Perform the application related copying and configuration based on your organisation and validate them as well.
    
* 13- Check for the DNS update and under route53 test the record.
    
* 14- Test application
    
* 15- Finalize cutover
    
* 16- Mark as archived
    
* 17- Check in fleet manager if there are connecion lost status of ssm agents and duplicated instances.