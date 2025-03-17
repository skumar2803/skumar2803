---
title: "Jenkins Freestyle & Simple declarative project."
datePublished: Tue Jun 13 2023 20:12:03 GMT+0000 (Coordinated Universal Time)
cuid: cliupypq7000309i6gqpe1ybm
slug: jenkins-freestyle-simple-declarative-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686685251717/26c891bc-b900-4502-8f41-7dbc9b21fadf.jpeg
tags: devops, hashnode, jenkins, devops-journey

---

Within this blog, I have illustrated two projects about freestyle and simple declarative and the concept of <mark>GitHub hook trigger</mark>.

I am trying to set up circle CI which will take some time as I am running into issues while configuring it. So my next blog will cover that.

**<mark>Project:&nbsp;&nbsp;&nbsp;&nbsp;Django-todo-app-delivery</mark>**

Click Create a Job and select <mark>Freestyle project</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686685387556/db056f7a-cc4e-4a8e-8122-9b459a4b3848.png align="center")

Select the checkboxes depending on the requirement and the explanation of each is mentioned here. Please zoom in for a better view :)

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686685502127/c9179246-6afb-4090-acc3-01165d38c764.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686685558541/f211d83e-a43e-4212-8bd5-b90c0ed08016.png align="center")

The project is ready and the below build steps

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686685657338/0a5a1b8f-7c6e-4bb2-a41d-1fd72aafec3b.png align="center")

Now click on the dashboard on the top left. If so build is successful, then click the play button on the right-most side.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686685746769/d87e77f1-59e7-4782-8f43-f301c755a4e4.png align="center")

On checking the console o/p i.e. build #6

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686685952518/19d8e281-f958-46a8-83a7-ef0e7dfca3a5.png align="center")

**<mark>GitHub Hook Trigger</mark>**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686168384/5d3aa0aa-3d33-4669-96c6-f15f78b879f6.png align="center")

A GitHub webhook trigger is an event or action that prompts GitHub to send a payload to a configured endpoint (URL) whenever the specified event occurs in a repository or organization. This enables you to automate processes or integrate external systems with your GitHub workflow.

To set up a webhook trigger in GitHub, you generally follow these steps:

1. Navigate to the repository or organization where you want to add the webhook.
    
2. Go to the "Settings" tab.
    
3. Look for the "Webhooks" or "Hooks" section and click on it.
    
4. Click on the "Add webhook" or "Create webhook" button.
    
5. Provide the required information, such as the Payload URL (the endpoint that will receive the webhook payload), the content type, and the events that should trigger the webhook.
    
6. Optionally, you can configure other settings, such as adding a secret for secure communication or selecting which SSL certificate to use.
    
7. Save or create the webhook.
    

Once the webhook trigger is set up, GitHub will send a POST request to the specified payload URL whenever the configured event occurs. The payload typically contains information about the event, such as the type of event, the repository, and relevant data.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686482729/05da31b9-52e5-4001-b5a9-d8947ce50d3d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686513064/7b6b4b74-4a14-408f-a25d-7e5270ac0c9a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686535997/2526ac6a-754d-4913-8a6c-2890475864ac.png align="center")

Now I can see the green tick on the right side, which is a clear indicator that my webhook is configured successfully.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686631988/7959da4d-6857-470e-9757-b47a63ad5fab.png align="center")

**<mark>Declarative pipe:</mark>**  
The Jenkins Declarative Pipeline is a domain-specific language (DSL) extension for Jenkins that allows you to define your build pipeline using a more structured and readable syntax. It provides a simplified way to create continuous delivery pipelines by using a declarative approach.

The advantage of a Declarative pipe is that it will show deployment as failed even if 1 of the stages fails.

Click create new and select the <mark>pipeline</mark>

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686870436/5afce741-77a9-41c0-8758-1336f0b5c997.png align="center")

Hit save and build now and click to see the details

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1686686925085/b7be67bc-ad13-4d2b-94b9-22183f56d007.png align="center")