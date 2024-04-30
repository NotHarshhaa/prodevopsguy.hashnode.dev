---
title: "Azure DevOps Series - Azure Artifacts"
datePublished: Tue Apr 30 2024 03:37:09 GMT+0000 (Coordinated Universal Time)
cuid: clvlu7ke1000309l0cjk372wq
slug: azure-devops-series-azure-artifacts
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714448154537/dd9bcbe3-7f11-44eb-82ec-b32ccb0d2911.png
tags: azure, devops, azure-devops, devops-articles, azuredevops-zero-to-hero

---

Azure Artifacts enables developers to efficiently manage all their dependencies from one place. With Azure Artifacts, developers can publish packages to their feeds and share them within their team, across organizations, and even publicly across the internet.

![](https://miro.medium.com/v2/resize:fit:802/1*yaEjE_hetPCgXKTK-9D6lg.png align="left")

Azure Artifacts if you need to share packages within the same team, across organizations, or even publicly.

Create a new project

![](https://miro.medium.com/v2/resize:fit:802/1*Xo8_iPrA-2uOcOuDnA0ADA.png align="left")

Goto azure repository → Import a repository

[https://github.com/Ibrahimsi/nike\_landing\_page.git](https://github.com/Ibrahimsi/nike_landing_page.git)

![](https://miro.medium.com/v2/resize:fit:802/1*lUTYbqy2laALknB2XgrD0Q.png align="left")

Successfully imported

![](https://miro.medium.com/v2/resize:fit:802/1*piuhqdrxtiWdi-FyDJVmvg.png align="left")

Create a Webapp in Azure portal

App Services → Create → Web App

![](https://miro.medium.com/v2/resize:fit:802/1*RxD7gKxjyCcKe6nnpmHR3g.png align="left")

Modify the configuration setting

**Note**: You must set the app settings as below to disable all file caching:

![](https://miro.medium.com/v2/resize:fit:802/1*jJqAodlKoXecJrOsFnITsg.png align="left")

Add 2 New application setting

```yaml
Name: WEBSITE_DYNAMIC_CACHE
Value: 0
```

![](https://miro.medium.com/v2/resize:fit:802/1*N0pgq9lYQdrdkKlEm2U17w.png align="left")

```yaml
Name: WEBSITE_ENABLE_SYNC_UPDATE_SITE
Value: never
```

![](https://miro.medium.com/v2/resize:fit:802/1*xadqYENMZaZkdpgJAZDJHA.png align="left")

Save the changes

![](https://miro.medium.com/v2/resize:fit:802/1*KSPzeJJ_7f0xVIVJAaVdmQ.png align="left")

If you click the URL the page is goes to default web page

![](https://miro.medium.com/v2/resize:fit:802/1*nA0oewfGbcoqgLWhe48wUA.png align="left")

Default web page is running on Azure

![](https://miro.medium.com/v2/resize:fit:802/1*dPzDtIWxLw2q73PhF47mAQ.png align="left")

# **Create a new pipeline**

Set of automated processes and tools that allows both developers and operations professionals to work cohesively to build and deploy code to a production environment.

Create Pipeline → Azure Repos Git → Day7\_Artifacts → Starter Pipeline

```yaml
trigger: 
- main

stages:
- stage: Build
  jobs:
  - job: Build
    pool:
      vmImage: 'ubuntu-latest'
    steps:
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'install -D tailwindcss postcss autoprefixer'
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'run build'
```

Organizational constructs that allow you to store, manage, and group your packages and control who to share it with.

Let’s Create a artifacts feed

![](https://miro.medium.com/v2/resize:fit:802/1*2ud0wezjTO6KfQykkwyIDg.png align="left")

Created

![](https://miro.medium.com/v2/resize:fit:802/1*txzdBV28uiiWpXI4OmdWcg.png align="left")

Again goto the pipelines click show assistant

![](https://miro.medium.com/v2/resize:fit:802/1*PUCaWlhKOIdh8yAsghOHwg.png align="left")

npm stands for Node Package Manager. It’s a library and registry for JavaScript software packages.

Add NPM

![](https://miro.medium.com/v2/resize:fit:802/1*6_N-Ox5MPGQHRw6nFd973Q.png align="left")

Add NPM the code automatically add to the pipelines

```yaml
trigger: 
- main

stages:
- stage: Build
  jobs:
  - job: Build
    pool:
      vmImage: 'ubuntu-latest'
    steps:
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'install -D tailwindcss postcss autoprefixer'
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'run build'
    - task: Npm@1
      inputs:
        command: 'publish'
        workingDir: './dist'
        publishRegistry: 'useFeed'
        publishFeed: '515a2edb-27f5-416f-88c0-0c50138edec1/336630b1-903f-4ae3-88c6-69149d01550e'
```

Pipeline Code

![](https://miro.medium.com/v2/resize:fit:802/1*Hrbx-afGt3KmV5ie42dnWw.png align="left")

Finally save the run Got some error

![](https://miro.medium.com/v2/resize:fit:802/1*S6RVCjmwwlluTtYThsMwDg.png align="left")

Goto azure artifacts given to the contributor access

Click the Feed Settings

![](https://miro.medium.com/v2/resize:fit:802/1*lhfs_pVJKR9GoTCZs07rzg.png align="left")

Remove the old one

![](https://miro.medium.com/v2/resize:fit:802/1*pF4Oq7xdqwoJOW8YwUujjw.png align="left")

Add the → **contributor** permission

Enables users to manage personal views, edit items and user information, delete versions in existing lists and document libraries and add, remove, and update personal Web Parts.

![](https://miro.medium.com/v2/resize:fit:802/1*4GmmyFObAJSWoK1LNL41aQ.png align="left")

Again run the pipeline. Change the version 1.3

![](https://miro.medium.com/v2/resize:fit:802/1*TMdXeZnqmKPi8Y_aQdpp-Q.png align="left")

Automatically trigger the pipeline

![](https://miro.medium.com/v2/resize:fit:802/1*SgwTmS7QeBrxOTjLWAr2SA.png align="left")

Goto the azure feed

![](https://miro.medium.com/v2/resize:fit:802/1*STVgEhfireouN3S60S6TAw.png align="left")

# **Create a release pipeline**

A Release Pipeline consumes the Artifacts and conducts follow-up actions within a multi-staging system.

Release pipeline is a process to ship committed code into production by incorporating CI/CD, automated testing, and finally, software release.

Pipelines → Releases → New Pipeline → Select → Azure App Service deployment

![](https://miro.medium.com/v2/resize:fit:802/1*h_mWyCAmuT9FbhGVpa3E5g.png align="left")

Given to the name → Deployment

![](https://miro.medium.com/v2/resize:fit:802/1*dX6d6GPYVNpKZiULYdb3zQ.png align="left")

Click Add an artifact → Azure artifacts

![](https://miro.medium.com/v2/resize:fit:802/1*f3aNm08V7MqT-Pa8yLNh7g.png align="left")

Enable the continuous deployment trigger

A trigger consists of a specified component, deployment process, and user.

![](https://miro.medium.com/v2/resize:fit:802/1*WoDzjgT_83sAkE3ilGbALg.png align="left")

Enter the stage name and select the subscription, Service name…

![](https://miro.medium.com/v2/resize:fit:802/1*as4DO4Yf4PGDoxKpsNb2Xw.png align="left")

Select the azure pipelines on agent pool.

An agent is a service that runs the jobs defined in your pipeline. The execution of these jobs can occur directly on the agent’s host machine or in containers.

![](https://miro.medium.com/v2/resize:fit:802/1*H1pbVoJ5b8K_4pa-XtcrrQ.png align="left")

Deploy Azure App Service

Added to the some script on app service.

```yaml
cp -rf /home/site/wwwroot/package/* /home/site/wwwroot/
```

![](https://miro.medium.com/v2/resize:fit:802/1*iVFbKDOaLXee4qZqoGaGDg.png align="left")

Save the all setting. Check the release pipelines there is no create

![](https://miro.medium.com/v2/resize:fit:802/1*bWzRiSA3dkB0_JytGGT9og.png align="left")

Goto azure artifact promote artifactory

![](https://miro.medium.com/v2/resize:fit:802/1*7AlPqyrEU_SMkWO6LhkCrQ.png align="left")

Pre-release means software, online services, and additional products and features that are provided for preview, beta, (or) early access versions. Click that Prerelease

![](https://miro.medium.com/v2/resize:fit:802/1*CiUunByInIK4a4UNb9eX9g.png align="left")

Check the release pipeline

![](https://miro.medium.com/v2/resize:fit:802/1*lHjLTZ4KAjKDW5xCYwbTkg.png align="left")

Deploy the stages

![](https://miro.medium.com/v2/resize:fit:802/1*yiPhE0dxPBbD7Vd4qow3VA.png align="left")

Job is completed

![](https://miro.medium.com/v2/resize:fit:802/1*e7c88xGmQ3T_O73DgGqodg.png align="left")

Check the URL

![](https://miro.medium.com/v2/resize:fit:802/1*tdM7OlWCRsyeq4e_kMdWPw.png align="left")

KUDU Console is a debugging service for Azure platform which allows you to explore your web app and surf the bugs present on it, like deployment logs, memory dump, and uploading files to your web app, and adding JSON endpoints to your web apps…

Kudu gives you helpful information about your App Service app, Such as App settings. Connection strings. Environment variables.

Diagnostic and troubleshooting purposes when your function or function host fails.

![](https://miro.medium.com/v2/resize:fit:802/1*6J0H60ZEbKFeKFt1MdwaXA.png align="left")

Redirect the console

![](https://miro.medium.com/v2/resize:fit:802/1*7kmdrhpP25GDR59MVAzFFA.png align="left")

Click an SSH you should able to the access in web app

![](https://miro.medium.com/v2/resize:fit:802/1*SPUcKD915bSeIPjP8_8U4Q.png align="left")

File created before 10 minutes

Thank you 🙏 for taking the time to read our blog.