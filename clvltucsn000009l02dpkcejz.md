---
title: "Azure DevOps Series - Azure Boards"
datePublished: Tue Apr 30 2024 03:26:53 GMT+0000 (Coordinated Universal Time)
cuid: clvltucsn000009l02dpkcejz
slug: azure-devops-series-azure-boards
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714447457476/90f559aa-6abb-4a16-93f0-7419ffb0713f.png
tags: azure, devops, azure-devops, devops-articles, azuredevops-zero-to-hero

---

Azure Boards is a service for managing the work for your software projects. Teams need tools that flex and grow.

![](https://miro.medium.com/v2/resize:fit:802/1*93M3TcoAJYyJkqBQoeJnvQ.png align="left")

**Azure Boards**

**Azure Boards** does just that, brining you a rich set of capabilities including native support for Scrum and Kanban, customizable dashboards, and integrated reporting. Here you are aided by three work item types:

* Epics
    
* Issues
    
* Tasks
    

![](https://miro.medium.com/v2/resize:fit:559/1*IVhTc0n-yvUeXaXckSAYbQ.png align="left")

Also as the work gets completed the status gets updated stage by stage from:

* To Do
    
* Doing
    
* Done
    

Here is the image below depicting the same

![](https://miro.medium.com/v2/resize:fit:486/1*WfkQTpIcDSPqDFl4dARlGA.png align="left")

Each time we create or add an issue, task or an epic, it means we are creating a work item.

Useful links below, hope it helps.

[Choose a process](https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/choose-process?view=azure-devops&tabs=basic-process) ← Process

[Agile workflow](https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/agile-process-workflow?view=azure-devops) ← Agile

[CMMI workflow](https://docs.microsoft.com/en-us/azure/devops/boards/work-items/guidance/cmmi-process-workflow?view=azure-devops) ← CMMI

> ***Agile*** *is an iterative approach to project management and software development that helps teams deliver value to their customers faster and with fewer headaches.*
> 
> *The Capability Maturity Model Integration (CMMI) is a model that helps organizations to: Effectuate process improvement. Develop behaviors that decrease risks in service, product, and software development*

# **Azure Boards Processes**

1. Basic: Choose Basic when your team wants the simplest model that uses Issues, Tasks, and Epics to track work.
    
2. Agile: Methodology is a way to manage a project by breaking it up into several phases.
    
3. Scrum: Framework for creating and maintaining a consistent rate of work for complex projects.
    
4. CMMI: Structured collection of best practices in engineering, service delivery and management, which aims to assist companies improve their ability to deliver customer satisfaction through an ever increasing understanding of their capabilities.
    

![](https://miro.medium.com/v2/resize:fit:802/1*XOPRpxIEnj9lyZZYi8uvIg.png align="left")

The basic process contains three work item types:

* **Epics**: Group your more significant items into Epics such as Website updates, Cloud migration, CICD implementation
    
* **Issues**: Further divide your Epics into Issues such as Homepage, about us page, secure sign-in
    
* **Task**: Tasks are the smallest amount of work that can be assigned to someone, for example, designing a homepage header, standardizing fonts, and fixing the homepage CSS to make it mobile responsive.
    

[**Read more**](https://dev.to/ibrahimsi/azure-board-devops-57bp) **← Azure Boards**

# **Defining Teams and Work Items**

# **What is a Work Item:**

A work item can track all types of activities. It could be a

* Task to do
    
* A bug to fix,
    
* An issue or anything that we can assign to people and keep track of the progress.
    

![](https://miro.medium.com/v2/resize:fit:802/1*wVhcZv8NVQtdpIXKqvU2fA.png align="left")

# **Kanban Board**

**Kanban** is a visual system for managing work as it moves through a process. Kanbanvisualizes both the process (the workflow) and the actual work passing through that process.

Kanban has two significant elements namely:

1. Cards
    
2. Boards
    

The board can be **physical**, but the software team has a preference towards **virtual board** as this could be easily accessed from various locations and thus makes the team collaboration more proficient.

Usually, the board can be split into three sections namely:

1. To-Do
    
2. In Progress
    
3. Done
    

**Basic principles associated with the Kanban process**

1. Visualize the workflow
    
2. Limit work in progress
    
3. Managing the workflow
    
4. Make explicit process policies
    
5. Implement feedback loops
    
6. Continuous Improvement
    

# **Hands-On**

Create a new project

![](https://miro.medium.com/v2/resize:fit:802/1*uoRr46kxmB944IzfMvktBA.png align="left")

Click left side Boards → Boards

![](https://miro.medium.com/v2/resize:fit:802/1*IMl1HupngzxhlfqXMZQoZQ.png align="left")

This is a todo list template or notion template and this a board view.

![](https://miro.medium.com/v2/resize:fit:802/1*OODEOg8JaKun8ukHq7yaqw.png align="left")

Swithch on the view as backlog. Using create a workitem and list over here.

![](https://miro.medium.com/v2/resize:fit:802/1*iUomLkeDlSccdZCKtNQ3DA.png align="left")

Lets go to the board view and lets try to add the work items.

![](https://miro.medium.com/v2/resize:fit:802/1*pNM3rbTYlr1bUApTyqN19A.png align="left")

Two types of workitem here

1. Epics
    
2. Issues
    

Create a workitem

![](https://miro.medium.com/v2/resize:fit:802/1*gbPMaNZccbMD-7LVK8uqvA.png align="left")

Click on the workitem it will be expand. So you can add more details

![](https://miro.medium.com/v2/resize:fit:802/1*58KiVRRGJUqalRyR_QuAog.png align="left")

Created a first workitem which is to-do state

![](https://miro.medium.com/v2/resize:fit:802/1*gxzQcfi3pjXE62dSSJ4bZg.png align="left")

Create a new issues workitem and add to the task

![](https://miro.medium.com/v2/resize:fit:802/1*hDSIZmYIwGzMAhJt5s65Tg.png align="left")

Expand the website homepage workitems. Add a description after save and close.

![](https://miro.medium.com/v2/resize:fit:802/1*WCySoYpSUOcV8-BPVZkcXQ.png align="left")

Click the particular task add the activity

![](https://miro.medium.com/v2/resize:fit:802/1*kY4cxi_ifujn59wBkx7L-w.png align="left")

Lets move to the workitem the task is complete.

![](https://miro.medium.com/v2/resize:fit:802/1*AbU-bydh4aI3qpErZ0d7Uw.png align="left")

We will go the advanced concept → Scrum

Go to this link → [https://azuredevopsdemogenerator.azurewebsites.net/](https://azuredevopsdemogenerator.azurewebsites.net/) → Sign In

Generates from dummy data in our project.

![](https://miro.medium.com/v2/resize:fit:802/1*soIYjSTceDH1w_Lhroq-AA.png align="left")

Create a new project → Select a template & Organization

![](https://miro.medium.com/v2/resize:fit:802/1*lQs8WcrfTN5fDMpzNSh91Q.png align="left")

How to check the project created or not? Goto the organization the project showing

![](https://miro.medium.com/v2/resize:fit:802/1*fAyuYMXUps2SLQ0bpT7KGg.png align="left")

Make some changes in project setting

![](https://miro.medium.com/v2/resize:fit:802/1*KqRsbUUakWf8Anabja2BeQ.png align="left")

Create a new team

![](https://miro.medium.com/v2/resize:fit:802/1*vJXn-m0KIaByOlcKZTGZOA.png align="left")

Open the PUL-Web after click iteration and access paths

![](https://miro.medium.com/v2/resize:fit:802/1*X5tW9nL8_oclfQ-IvARvVQ.png align="left")

Goto iteration tab and add to the sprint

![](https://miro.medium.com/v2/resize:fit:802/1*S-Wzdvk36tl3y-KQGDqjbg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*o6pEY7_9vb6z0v_YC_1E8g.png align="left")

Goto my dashboard → Click Overview

![](https://miro.medium.com/v2/resize:fit:802/1*siADDYyw7c6SRtnt4pgG6g.png align="left")

Create a new workitems add sprint2

![](https://miro.medium.com/v2/resize:fit:802/1*ZkjH3h2tUy78ZEKsncPfWg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*CYCKhc5v_UG7PKtLgbF7xg.png align="left")

Goto boards → work items. If you have check the workitems created or not?

![](https://miro.medium.com/v2/resize:fit:802/1*n-2JcHJFaYAY6O_Ska_IPQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*amycT63ix4jJMws8cOKaWQ.png align="left")

Add to the child work items

![](https://miro.medium.com/v2/resize:fit:802/1*MTmStJb5Af0T7EuGZKgoaQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*gLMWOx37fEYVwzgQZUcjRg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*Jp7iGRoNr5xX9tlplQbcBA.png align="left")

Goto the boars → My team boards → PUL-Web boards

![](https://miro.medium.com/v2/resize:fit:802/1*m0fT3XniCKKGxnHmii2nxg.png align="left")

Change the features state → Add Product Backlog Item

![](https://miro.medium.com/v2/resize:fit:802/1*6SqLWPQOCt5xYlKxZCEOYA.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*dj_6hCifanR75ErDIxJM8Q.png align="left")

Goto the View as backlog you can approve the separate features and assign to the task particular members.

![](https://miro.medium.com/v2/resize:fit:802/1*ffKrHg-ItboaqIkCZ497BQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*fnsD9Qek1svOsBYoRCjm4w.png align="left")

Click view as backlog → to create a task another way

![](https://miro.medium.com/v2/resize:fit:802/1*foND7XplNUCElVSdTIZGzg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*1sbR2NBsxMecSWjc6RfpYw.png align="left")

Sprint means a fixed period of time during which the team commit and work towards a fixed goal which does not change.

![](https://miro.medium.com/v2/resize:fit:802/1*SHuJgyWNK_yy6OJkQ7zl7Q.png align="left")

There is no changes in particular project

![](https://miro.medium.com/v2/resize:fit:802/1*6hZUIU3oZ5OHKvDKoohXmw.png align="left")

So if you change the project

![](https://miro.medium.com/v2/resize:fit:802/1*auHyxJHR6TN9gHWsfuB5NQ.png align="left")

Now you add itetation. Goto Project setting → Team Configuration → Iterations

![](https://miro.medium.com/v2/resize:fit:802/1*_7fDQirZ8vYqQZICsqEMRA.png align="left")

It shows the sprints

![](https://miro.medium.com/v2/resize:fit:802/1*LrQiO-2C601HdicIrJ2L0A.png align="left")

Assign to someone → Sometask

![](https://miro.medium.com/v2/resize:fit:802/1*RPMDUnaQfkxzXg2XsmZoZQ.png align="left")

Capacity → adjust the team planning

![](https://miro.medium.com/v2/resize:fit:802/1*3Etm_APCGnEdA70sS_uxAA.png align="left")

Goto the taskboard

![](https://miro.medium.com/v2/resize:fit:802/1*g4lnvuzL2HnuxgV_i0y2AQ.png align="left")

Modify the task the working hours automatically change

![](https://miro.medium.com/v2/resize:fit:802/1*FGCj-8H5n4LgnT8F8Lv46A.png align="left")

Or let move to the another sprint in particular tasks

![](https://miro.medium.com/v2/resize:fit:802/1*nbbRg8B8pwAmHZwzo8L1Dw.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*MQ03CTKaYeiVg_0rDA4EKw.png align="left")

Lets check the sprint 3

![](https://miro.medium.com/v2/resize:fit:802/1*a7cfDwYkEwYGEmXWvkcfeQ.png align="left")

Easily identify the some color technique. Goto setting

![](https://miro.medium.com/v2/resize:fit:802/1*WrjfRJ5GtlkIuNW3sv3V5Q.png align="left")

Go and check the development the color will be change

![](https://miro.medium.com/v2/resize:fit:802/1*oUb9Fr-2G1L1OWW2SuLstQ.png align="left")

Changed the p1 issue show the red color

![](https://miro.medium.com/v2/resize:fit:802/1*5yzCLqWH9EW_XOfpEmkOiQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*aclVNQPoAYddNE44ts2qtg.png align="left")

I change the priority select 1 color will automatically change

![](https://miro.medium.com/v2/resize:fit:802/1*cLjNDmaUYGXIsIBC1aomkA.png align="left")

Other setting will be change → tag color

![](https://miro.medium.com/v2/resize:fit:802/1*x35r4pCg7GtjJNCjcJpsFQ.png align="left")

Add tag

![](https://miro.medium.com/v2/resize:fit:802/1*Dn0sEwEmTMgoLZvw7KyjSg.png align="left")

The automatically change the data tag

![](https://miro.medium.com/v2/resize:fit:802/1*5jHaviS2HbhMFHIx1WHIcQ.png align="left")

One more column add in work items

![](https://miro.medium.com/v2/resize:fit:802/1*AqrbSzWogQ09ZI42zHduvg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*Zt2iqOyQKeUk9Jy7OIrd_w.png align="left")

Split the column

![](https://miro.medium.com/v2/resize:fit:802/1*1jDxZSE-JeayftBWPVL-Vw.png align="left")

Swimlanes → Track the more items

![](https://miro.medium.com/v2/resize:fit:802/1*VZ5RMbNrbapG7NylKUj0Ng.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*ftpb6FfZ0qnnQ0K4e6fXtA.png align="left")

Now check the another workitem

![](https://miro.medium.com/v2/resize:fit:802/1*VMt4bWNuzBmuGw6TiuSSjQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*ZUbaatqeBkA57i35cNm21g.png align="left")

# **How to create a Custom dashboard**

Dashboards → New dashboard

![](https://miro.medium.com/v2/resize:fit:802/1*cbhxeNAHKocfJtbHR6FItQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*uSB0bYlORSdi9PPcawF67w.png align="left")

Add a Widget → Sprint Overview → Click Configure

![](https://miro.medium.com/v2/resize:fit:802/1*cVR8qJjpKsjvGrfDO0JhGA.png align="left")

Add anothet widget → Sprint Capacity → Select the team → PUL Web

![](https://miro.medium.com/v2/resize:fit:802/1*USbsMsMGacdlen1qrdTmBA.png align="left")

Goto boards → queries → New query → Create a custom query

![](https://miro.medium.com/v2/resize:fit:802/1*EKWrX-xF91KvTugmFlSgOg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*en-W-_lhWHX73jr9qKORSA.png align="left")

Add Charts → New

![](https://miro.medium.com/v2/resize:fit:802/1*9zvpsz7E6UUtvN0GkHj_RA.png align="left")

Save all → Click save as

![](https://miro.medium.com/v2/resize:fit:802/1*iWoUvs3NnA5yKChq-uJIfw.png align="left")

Shared queries → Queries shared across the board.

Goto chart → Add new chart → Assigned to → Save

![](https://miro.medium.com/v2/resize:fit:802/1*dPvNPkOav7I1M-0RV1yHNw.png align="left")

Add to dashboard

![](https://miro.medium.com/v2/resize:fit:802/1*dwskaoO98rPXm8nq0MKhLA.png align="left")

The chart is added to dashboards

![](https://miro.medium.com/v2/resize:fit:802/1*h76yKr8RxKtliaG-q9jN8A.png align="left")

Click Edit button → Chart for Work Items → Add

![](https://miro.medium.com/v2/resize:fit:802/1*0ULWqpjnoKjNncyOi4OBBQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*lmN1KYZ6iORqez3-1rVuAA.png align="left")

Click Configure

![](https://miro.medium.com/v2/resize:fit:802/1*z1RUQif0txlChLp1xEkUjQ.png align="left")

Customize the team process

Goto Organization setting → Process → Scrum → Create inherited process

![](https://miro.medium.com/v2/resize:fit:802/1*jBt4sj87n48cZtgTIv0fDA.png align="left")

Create a process

![](https://miro.medium.com/v2/resize:fit:802/1*oc3g0ao8u13h3Y5sgJKOIA.png align="left")

Click the Customized Scrum → Product Backlog Item

![](https://miro.medium.com/v2/resize:fit:802/1*B43DtDrfM269LQ29EWkRkg.png align="left")

Add → New field → Click Add field

![](https://miro.medium.com/v2/resize:fit:802/1*th9gNxq-OqMprH-a2nOteQ.png align="left")

Goto All processes → Scrum → Projects → Parts Unlimited → Change Process

![](https://miro.medium.com/v2/resize:fit:802/1*j_rAmIYjOo1243QF252cCg.png align="left")

Save — Customized Scrum

![](https://miro.medium.com/v2/resize:fit:802/1*49t1WudGFe-OsW6tHrwSYg.png align="left")

Goto our project → Parts Unlimited → Boards → Work Items

![](https://miro.medium.com/v2/resize:fit:802/1*fykjL0UaoE55N7OWdPRiMQ.png align="left")

The Ticket ID has been created

![](https://miro.medium.com/v2/resize:fit:802/1*9QpAFsGFimdC_cxhGegL6w.png align="left")

If you create a new project the work item process show the customised process….

![](https://miro.medium.com/v2/resize:fit:802/1*cSNgvMBR_HXrQGh4L6DrNA.png align="left")

Thanks for reading…I hope it would be more helpful for understand the Azure Boards.!