---
title: "Azure DevOps: YAML Pipeline Tutorial, Setting up CI/CD using YAML Pipeline, Multi Stage/Job Setup."
datePublished: Sat Oct 07 2023 16:48:35 GMT+0000 (Coordinated Universal Time)
cuid: clng9rvkj000409mqagv4f301
slug: azure-devops-yaml-pipeline-tutorial-setting-up-cicd-using-yaml-pipeline-multi-stagejob-setup
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696695967036/ad0c0d09-436f-487b-aba7-30ac2faf8a4c.jpeg
tags: github, azure, devops, azure-devops, ci-cd

---

### Introduction

This article is for understanding the core concept of the YAML Pipeline in Azure DevOps. Further it describes how you can write your own YAML file to implement **CI/CD**.

### What is YAML

YAML is a human-readable data-serialization language and it helps to configure pipelines as a Code.

Indentation is very important in YAML.

### YAML Pipeline

In Azure DevOps, Pipelines help to set up **Continuous Integration/ Continuous Deployment** and to achieve this we have the below two options.

1\. Classic Editor

**2\. YAML Pipeline.**

In this Document, we will discuss the setup **YAML Pipeline.**

### **YAML Pipeline Structure**

![](https://static.wixstatic.com/media/33586b_241db7a149f34a55907fe398800c91ac~mv2.png/v1/fill/w_779,h_702,al_c,q_90,usm_0.66_1.00_0.01,enc_auto/33586b_241db7a149f34a55907fe398800c91ac~mv2.png align="center")

### **Hierarchy of YAML File**

```yaml
stages:
- stage: Build
  jobs:
  - job: BuildPackage
    steps:
    - Build
    - Package
    - Publish
- stage: Deploy
  jobs:
  - job: startDeployment
    steps:
    - Deploypackage
```

![](https://static.wixstatic.com/media/33586b_7946d79f23cb429d99d977e07ed8ec36~mv2.png/v1/fill/w_379,h_234,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/33586b_7946d79f23cb429d99d977e07ed8ec36~mv2.png align="left")

### Component of YAML Pipeline

Here is the list of components that we use in YAML pipeline creation.

### 1\. Stages

The stage is a collection of Jobs that runs sequentially.

```yaml
stages:
- stage: Build
  jobs:
  - job: BuildOnWindows
    steps:
    - Build
  - job: BuildOnMac
    steps:
    - Build
```

### 2\. Jobs

Job is a Collection of Steps that runs on agents/environment.

```yaml
jobs:
- job: BuildPackage
  steps:
  - Build
  - Package
  - Publish
```

### 3\. Steps

Steps help to define the set of processes to set up your task or any activity that you want to perform on any specific job.

**Kind of Steps:**

* Task
    
* Script
    
* template reference
    

```yaml
steps:
- Build
- Package
- Publish
```

### Schema of YAML Pipeline file.

```yaml
name: string # Define Custom Build number/Name
variables: #Define variable for Pipeline 
trigger: trigger/none #it defines which branch to enable for CI
stages:[stage| templateReference ]
  jobs:[job| templateReference ]
    steps:[script | task | templateReference ]
```

### Important Note:-

1. In some cases, if there is only one stage required for the pipeline we can omit the stage keyword and can directly start from Jobs.
    
2. In some build setups where only one agent is required for the pipeline in that case we can omit Job and directly define the Steps.
    

### DEMO:

We can begin with the demo to set up the YAML pipeline for below three scenarios below.

> **Single Stage, Single Job YAML Pipeline**

> **Single Stage Multi Job YAML Pipeline**

> **Multi-Stage YAML Pipeline**

### 1\. Single Stage, Single Job YAML Pipeline

Assume that you have been assigned to set up a build for an application. In this scenario, we can omit stages or Jobs.

```yaml
name: sampleWeb_$(Date:yyyyMMdd)$(Rev:.r)
trigger:
- main
pool:
  name: Default
steps:
- task: VSBuild@1
  inputs:
    solution: '**\*.sln'
    msbuildArgs: '/p:DeployOnBuild=true /p:WebPublishMethod=Package 
 /p:PackageAsSingleFile=true /p:SkipInvalidConfigurations=true /p:PackageLocation="$(build.artifactstagingdirectory)\\"'
    platform: 'any cpu'
    configuration: 'release'
```

Here you can notice that we did not include the Stage and Job section in the YAML pipeline as it is not required in this scenario.

### 2\. Single Stage Multi Job YAML Pipeline

Let's assume you have to perform some activity on different Agents. Like building applications on Windows, Mac OS, and Linux. In this scenario, we can create multiple jobs and each job can be assigned with the respective agent.

```yaml
name: sampleWeb_$(Date:yyyyMMdd)$(Rev:.r)
trigger:
- main
jobs:
- job: ActivityonLinux
  pool:
   name: default
  steps:
  - script: echo Hello, world!
    displayName: 'Run a one-line script'
- job: ActivityonWindows
  pool:
   name: Default
  steps:
   - task: PowerShell@2
     inputs:
       targetType: 'inline'
       script: |
         # Write your PowerShell commands here.
         
         Write-Host "Hello World"
```

### 3\. Multi-Stage YAML Pipeline.

In this scenario, you have assigned one application where you need to build the Project and package it. After that, you need to deploy the application. In this case, we can create two stages.

**Stage1 --&gt; Build the Application**

**Stage 2 --&gt; Deploy the Application**

```yaml
name: sampleApp_$(Date:yyyyMMdd)$(Rev:.r)
trigger:
- main
stages:
- stage: Build
  jobs:
  - job: Build
    pool:
     name: Default
    workspace:
     clean: outputs 
    steps:
    - task: VSBuild@1
      inputs:
        solution: '**\*.sln'
        msbuildArgs: '/p:DeployOnBuild=true /p:WebPublishMethod=Package /p:PackageAsSingleFile=true /p:SkipInvalidConfigurations=true /p:PackageLocation="$(build.artifactstagingdirectory)\\"'
        platform: 'any cpu'
        configuration: 'release'
    - task: PublishBuildArtifacts@1
      inputs:
        PathtoPublish: '$(Build.ArtifactStagingDirectory)'
        ArtifactName: 'drop'
        publishLocation: 'Container'
- stage: Deploy
  jobs:
  - job: DeployWeb
    pool:
      name: Default
    steps:
    - powershell: "write-host"
    - task: DownloadBuildArtifacts@1
      inputs:
        buildType: 'specific'
        project: '0a1af395-65ea-473b-b60e-01fdc0d3f93e'
        pipeline: '11'
        buildVersionToDownload: 'latest'
        downloadType: 'single'
        downloadPath: '$(System.ArtifactsDirectory)'
    - task: AzureRmWebAppDeployment@4
      inputs:
        ConnectionType: 'AzureRM'
        azureSubscription: 'testconn'
        appType: 'webApp'
        WebAppName: 'demotest0103'
        packageForLinux: '$(System.ArtifactsDirectory)/**/*.zip'
```

If you find this article helpful then you can [**buy me a coffee**](https://www.buymeacoffee.com/harshhaareddy)**.**

Follow for more stories like this 😊/ [**GitHub**](https://github.com/NotHarshhaa)**.**