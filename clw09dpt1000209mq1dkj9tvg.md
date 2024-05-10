---
title: "Azure DevOps Series - Azure Pipeline"
datePublished: Fri May 10 2024 05:50:37 GMT+0000 (Coordinated Universal Time)
cuid: clw09dpt1000209mq1dkj9tvg
slug: azure-devops-series-azure-pipeline

---


Azure Pipelines automatically builds and tests code projects. It supports all major languages and project types and combines continuous integration, continuous delivery, and continuous testing to build, test, and deliver your code to any destination.

An Azure SPN is a security identity used by user-created applications, services, and automation tools to access specific Azure resources.

This access is restricted by the roles assigned to the service principal, giving you control over which resources can be accessed and at which level.

The service principal name (SPN) is the name that a client uses to identify a service for mutual authentication.

Clone the repository [**https://github.com/Ibrahimsi/Youtube\_clone.git**](https://github.com/Ibrahimsi/Youtube_clone.git)

![](https://miro.medium.com/v2/resize:fit:802/1*ShQJ-4ftUOe7Vd6lYx3OPw.png align="left")

Go to the azure devops portal create a new project

![](https://miro.medium.com/v2/resize:fit:802/1*riD9L9Hvx4ZRBBi8c5oJNw.png align="left")

Go to the azure repo copy the code

![](https://miro.medium.com/v2/resize:fit:802/1*8zWHPvupt6kR3Z_MtV7YxA.png align="left")

Paste the location of the folder terminal

![](https://miro.medium.com/v2/resize:fit:802/1*4wxAgxQm9221CJy_AM6KZg.png align="left")

Check the code is update for azure repo

```bash
git remote show origin
```

![](https://miro.medium.com/v2/resize:fit:802/1*G28HvPy6zWJ1JcChXAcW1A.png align="left")

Not update the remote repository remove that and again add to the azure devops remote repo.

```bash
git remote remove origin
git remote add origin https://Ibrahimsi909@dev.azure.com/Ibrahimsi909/Youtube%20Clone/_git/Youtube%20Clone
git push -u origin --all
```

![](https://miro.medium.com/v2/resize:fit:802/1*4isDM27zy5SeXuH2JbXiSg.png align="left")

Check devops portal the code is updated?

![](https://miro.medium.com/v2/resize:fit:802/1*OQniz6YzO3Q1eJ8SKWOXEA.png align="left")

# **Create a webapp from azure portal**

Azure App Services is a platform for building, deploying, and scaling web applications and services. It offers a variety of services, each with its own unique capabilities and use cases.

Azure App Service is an HTTP-based service for hosting web applications, REST APIs, and mobile back ends. You can develop in your favorite language, be it . NET, . NET Core, Java, Node. js, PHP, and Python.

Go to → weapp → Create a webapp

![](https://miro.medium.com/v2/resize:fit:802/1*SrEaxw4gZ485ckxHOVmVDA.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*yNV1oP1Ph0_89MaE-tQIEQ.png align="left")

Once created a webapp the website is ready

![](https://miro.medium.com/v2/resize:fit:802/1*KutNbAiVPf4k6ItGKr2HHQ.png align="left")

Check the default domain **ibrahimsi.azurewebsites.net**

![](https://miro.medium.com/v2/resize:fit:802/1*um30I9McR3qdxq7KZrIcCg.png align="left")

# **Create a Pipeline**

Go to pipeline → Create a pipeline → Click classic editor

![](https://miro.medium.com/v2/resize:fit:802/1*fG-V2Qf8_TcQ0cvo45EgtQ.png align="left")

Select Azure Repos Git → Select repo → Click Continue

![](https://miro.medium.com/v2/resize:fit:802/1*RbVRrbtAROw5q2QQDAlM4A.png align="left")

Select a template click Empty job

![](https://miro.medium.com/v2/resize:fit:802/1*ugdcArP9DXbUsiP7RHGDhQ.png align="left")

Add another agent

![](https://miro.medium.com/v2/resize:fit:802/1*xqsXAGcYi99GJsK4MMQe1w.png align="left")

Add the agent

1. npm install
    
2. npm build
    
3. Publish artifact
    
4. Azure app service deploy
    

![](https://miro.medium.com/v2/resize:fit:802/1*iMKowE4sbv9me1_DEfE3ag.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*jJH9VAxSZ6393sOyqrbARw.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*3X62BmTbexvcxPgF6NeIRQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*mMxLF0uMxqUr7g1u5sS1_Q.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*LqEKWFtVLho4YF_FYsUkxg.png align="left")

4 Task are set remaining variable,trigger see on later release handson. Click save and queue.

![](https://miro.medium.com/v2/resize:fit:802/1*E7sikK8pB-2Z7LPVT5jvAg.png align="left")

Finally save the pipeline

![](https://miro.medium.com/v2/resize:fit:802/1*7en2ZcWECzhmZHfXABuECw.png align="left")

If you faced problem some error

**“Error: No hosted parallelism has been purchased or granted. To request a free parallelism grant”**

![](https://miro.medium.com/v2/resize:fit:802/1*ClSuK4E43V2Ok4TG6InNcQ.png align="left")

Follow the below steps:

![](https://miro.medium.com/v2/resize:fit:802/1*JiPEzZwBau0b5uyBtuRtXQ.png align="left")

Finally run the pipeline

![](https://miro.medium.com/v2/resize:fit:802/1*HM0PBThhUSV_GJ6dTrX_fg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*0HcyN-ZblesLvOvQgXNeNQ.png align="left")

Click the URL the page redirect but the same default homepage

## [**Microsoft Azure App Service - Welcome**](https://ibrahimsi.azurewebsites.net/?source=post_page-----b6fe8d8505ba--------------------------------)

### [Edit description](https://ibrahimsi.azurewebsites.net/?source=post_page-----b6fe8d8505ba--------------------------------)

[ibrahimsi.azurewebsites.net](https://ibrahimsi.azurewebsites.net/?source=post_page-----b6fe8d8505ba--------------------------------)

![](https://miro.medium.com/v2/resize:fit:802/1*FaUYAGmRIwqZtt6DBCsd7Q.png align="left")

Why?

Default enable the cache in app services disable it now.

Go to azure portal → Webapp → Configuration → Finally save the setting

![](https://miro.medium.com/v2/resize:fit:802/1*ffb-OgbQ_jC2y38yQDFJbA.png align="left")

Restart the webservice application. Again hit the URL [https://ibrahimsi.azurewebsites.net/](https://ibrahimsi.azurewebsites.net/)

![](https://miro.medium.com/v2/resize:fit:802/1*t7cEphZU5AHFEcQAuSvRrQ.png align="left")

Successfully hosted the applications…

Export to pipeline

![](https://miro.medium.com/v2/resize:fit:802/1*3j8kMJaQj1fkWcrlS0LB9Q.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*G--MEdPSWk7Xm74sK5FAdA.png align="left")

YAML code

# **Another way to create a pipeline**

Pipeline → New pipeline → Azure repos git → Youtube Clone → Starter pipeline → Save and run

![](https://miro.medium.com/v2/resize:fit:802/1*JgHR_OM276C9jDsGU4SkJA.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*uIrZ5ds7hvdMM8c_8aPDLg.png align="left")

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
        command: 'install'
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'run build'

    
    - task: PublishBuildArtifacts@1
      inputs:
        PathtoPublish: 'build'
        ArtifactName: 'drop'
        publishLocation: 'Container'

- stage: Deploy 
  jobs:
  - job: Deploy
    pool:
      vmImage: 'ubuntu-latest'
    steps:
    - task: DownloadBuildArtifacts@1
      inputs:
        buildType: 'current'
        downloadType: 'single'
        artifactName: 'drop'
        downloadPath: '$(System.ArtifactsDirectory)'
    - task: AzureRmWebAppDeployment@4
      inputs:
        ConnectionType: 'AzureRM'
        azureSubscription: 'f2d858b2-0b52-4d8e-a750-adae9358c49a'
        appType: 'webAppLinux'
        WebAppName: 'ibrahimsi'
        packageForLinux: '$(System.ArtifactsDirectory)/drop'
        RuntimeStack: 'STATICSITE|1.0'
```

Finally run the code

![](https://miro.medium.com/v2/resize:fit:802/1*vpnEeuypyqOfQlMlJjrnEQ.png align="left")

Successfully completed the job

![](https://miro.medium.com/v2/resize:fit:802/1*WKpWqViIGqdAlE4NPkfOqA.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*JsaxQTmJbB3PPst2a1sofg.png align="left")

Rehit the URL

## [**Microsoft Azure App Service - Welcome**](https://ibrahimsi.azurewebsites.net/?source=post_page-----b6fe8d8505ba--------------------------------)

### [Edit description](https://ibrahimsi.azurewebsites.net/?source=post_page-----b6fe8d8505ba--------------------------------)

[ibrahimsi.azurewebsites.net](https://ibrahimsi.azurewebsites.net/?source=post_page-----b6fe8d8505ba--------------------------------)

![](https://miro.medium.com/v2/resize:fit:802/1*hDGaqPwrmPP6wT9DWAcbaQ.png align="left")

Thank you 🙏 for taking the time to read our blog.