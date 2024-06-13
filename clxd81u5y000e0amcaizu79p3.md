---
title: "The Ultimate DevOps Bootcamp Syllabus"
datePublished: Thu Jun 13 2024 12:14:06 GMT+0000 (Coordinated Universal Time)
cuid: clxd81u5y000e0amcaizu79p3
slug: the-ultimate-devops-bootcamp-syllabus
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1718280631945/bf5a7cbd-2d47-43b6-861a-ea042250fe0a.jpeg

---

# DevOps Bootcamp Curriculum:

### [<mark>Main Post Link</mark>](https://blog.prodevopsguy.xyz/the-ultimate-devops-bootcamp-2024-pack-by-prodevopsguy)

## Lesson 01: DevOps Bootcamp Overview

## Lesson 02: DevOps Overview

* **What is DevOps?**
    
* **Roles and Responsibilities of a DevOps Engineer**
    
* **How DevOps fits in the Software Development Lifecycle**
    

## Lecture 01: What is an OS and How Does it Work?

* **Tasks of an OS**
    
* **How an OS is Constructed**
    
* **Differences Between Unix, Linux, Windows, and MacOS**
    

## Lesson 02: Virtualization

* **Introduction to Virtual Machine**
    
* **Setup a Linux Virtual Machine**
    

## Lesson 03: Package Manager - Installing Software

* **What is a Package Manager and Software Repositories?**
    
* **Options for Installing Software on Linux and How it Works**
    
    * APT
        
    * APT vs APT-GET
        
    * SNAP
        
    * Ubuntu Software Center
        
    * YUM
        

## Lesson 04: Working with Vim Editor

* **What is Vim?**
    
* **Important Vim Commands**
    

## Lesson 05: Users & Permissions

* **Linux Accounts**
    
* **Users, Groups & Permissions**
    
* **User Management in Practice**
    
* **File Ownership & Permissions**
    
* **Modifying Permissions**
    

## Lesson 06: Linux File System

## Lesson 07: Basic Linux Commands

* **Introduction to Command Line Interface**
    
* **Essential Linux Commands**
    
    * Directory Operations
        
    * Navigating the File System
        
    * Working with the File System (Create folders, list files, rename, remove files, etc.)
        
    * Execute Commands as Superuser
        
    * Pipes, Redirects, Less, Grep
        

## Lesson 08: Shell Scripting

* **Shell vs sh vs Bash**
    
* **Write & Execute a Simple Script**
    
* **Writing Bash Scripts**
    
    * Variables
        
    * Conditional Statements
        
    * Basic Operators
        
    * Passing Arguments to a Script
        
    * Read User Input
        
    * Shell Loops
        
    * Functions
        

## Lesson 09: Environment Variables

* **What are Environment Variables and How to Access Them**
    
* **Create, Delete, and Persist Environment Variables**
    
* **Understanding the PATH Environment Variable**
    

## Lesson 10: Networking

* **How Computer Networks Work**
    
* **LAN, Switch, Router, Subnet, Firewall, Gateway**
    
* **IP Address and Port**
    
* **DNS and DNS Resolution**
    
* **Useful Networking Commands**
    

## Lesson 11: SSH - Secure Shell

* **What is SSH and How it Works**
    
* **SSH in Action**
    
    * Create Remote Server on Cloud
        
    * Generate SSH Key Pair
        
    * Execute a Bash Script on a Remote Machine
        

## Lesson 12: Introduction to Version Control and Git

* **Basic Concepts of Git**
    
* **Setup Git Repository (Remote and Local)**
    
* **Working with Git**
    
    * `git status`, `git commit`, `git add`, `git push`
        
* **Initialize Git Project Locally**
    
* **Concept of Branches**
    
* **Merge Requests**
    
* **Deleting Branches**
    
* **Avoiding Merge Commits (rebase)**
    
* **Resolving Merge Conflicts**
    
* **Ignoring Certain Files (.gitignore)**
    
* **Saving Work-in-Progress Changes (git stash)**
    
* **Going Back in History (git checkout)**
    
* **Undoing Commits (git revert, git reset)**
    
* **Merging Branches**
    
* **Git for DevOps**
    

## Lesson 13: Build Tools and Package Managers

* **What are Build Tools and Package Managers?**
    
* **Building an Artifact**
    
* **Running the Application Artifact**
    
* **Publishing the Application Artifact to an Artifact Repository**
    
* **Build Tools for Java (Gradle and Maven)**
    
* **Dependency Management in Software Development**
    
* **Package Manager in JavaScript Applications - Build and Run Applications in JS**
    
* **Build Tools & Docker**
    
* **Relevance of Build Tools for DevOps Engineers**
    

## Lesson 14: Cloud & Infrastructure as a Service Concepts

* **Setup Server on DigitalOcean (Droplet)**
    
* **Install Java on Cloud Server**
    
* **Deploy and Run an Application on Cloud Server**
    
* **Create a Linux User to Login to Server (Instead of Using Root User)**
    

## Lesson 15: Artifact Repository Manager

* **What is an Artifact Repository Manager?**
    
* **Install and Run Nexus on Cloud Server**
    
* **Different Repository Types (Proxy, Hosted, etc.)**
    
* **Different Repository Formats (Maven, Docker, NPM, etc.)**
    
* **Upload Jar File to Nexus (Maven and Gradle Projects)**
    
* **Nexus API and Repository URLs**
    
* **Blob Stores**
    
* **Browsing Components - Components vs Assets**
    
* **Cleanup Policies and Scheduled Tasks**
    

## Lesson 16: Introduction to Containers

* **What is a Container?**
    
* **Docker Components and Architecture**
    
* **Docker vs. Virtual Machine**
    
* **Main Docker Commands**
    
* **Debugging a Docker Container**
    
* **Demo Project Overview - Docker in Practice**
    
* **Developing with Containers**
    
* **Docker Compose - Running Multiple Services**
    
* **Dockerfile - Building Our Own Docker Image**
    
* **Private Docker Repository - Pushing Our Built Docker Image into a Private Registry on AWS**
    
* **Deploying a Containerized App**
    
* **Docker Volumes - Persist Data in Docker**
    
* **Volumes Demo - Configure Persistence for Our Demo Project**
    
* **Docker Best Practices**
    
* **Docker & Nexus**
    
    * Create Docker Images Repository on Nexus and Push/Pull Docker Image from/to Nexus Repository Manager
        
    * Deploy Nexus as Docker Container
        

## Lesson 17: Build Automation and Jenkins

* **What is Build Automation? What is Jenkins?**
    
* **Install Jenkins on Cloud Server (Docker vs Server Install)**
    
* **Jenkins Plugins**
    
* **Installing Build Tools in Jenkins**
    
* **Jenkins Basics Demo**
    
    * Create Freestyle Job
        
    * Configure Git Repository
        
    * Run Tests and Build Java Application
        
* **Docker in Jenkins**
    
    * Make Docker Commands Available in Jenkins
        
    * Build Docker Image
        
    * Push to DockerHub Repo
        
    * Push to Nexus Repo
        
* **Jenkins Pipeline (Use Cases)**
    
* **Create a Simple Pipeline Job**
    
* **Full Jenkinsfile Syntax Demo**
    
* **Create a Full Pipeline Job**
    
    * Build Java App
        
    * Build Docker Image
        
    * Push to Private DockerHub
        
* **Create a Multi-Branch Pipeline Job**
    
* **Credentials in Jenkins**
    
* **Jenkins Shared Library**
    
* **WebHooks - Trigger Jenkins Jobs Automatically**
    
* **Versioning Application in Continuous Deployment**
    
    * Concepts of Versioning in Software Development
        
    * Increment Application Version from Jenkins Pipeline
        
    * Set New Docker Image Version from Jenkins Pipeline
        
    * Commit Version Bump from Jenkins Pipeline
        

## Lesson 18: Introduction to Amazon Web Services

* **Create an AWS Account**
    
* **Identity & Access Management (IAM) - User, Groups, and Permissions**
    
* **Regions and Availability Zones**
    
* **Virtual Private Cloud (VPC) - Manage Private Network on AWS**
    
    * Subnets
        
    * Security Groups
        
    * Internet Gateway
        
    * Route Table
        
* **CIDR Blocks Explained**
    
* **Introduction to Elastic Compute Cloud (EC2)**
    
    * Create an EC2 Instance
        
    * Run Web Application on EC2 Using Docker
        
* **AWS Command Line Tool**
    
    * Install and Configure AWS CLI
        
    * Create AWS Components with AWS CLI
        
* **Automate Deploying from Jenkins Pipeline to EC2 Instance**
    
    * Using `docker run`
        
    * Using `docker-compose`
        
* **Real-Life Example of Dynamically Setting New Image Version in Docker-Compose**
    
* **SSH Agent Plugin and SSH Credential Type in Jenkins**
    

## Lesson 19: Introduction to Kubernetes

* **Understand the Main Kubernetes Components**
    
    * Node, Pod, Service, Ingress, ConfigMap, Secret, Volume, Deployment, StatefulSet
        
* **Kubernetes Architecture**
    
* **Minikube and kubectl - Local Setup**
    
* **Main Kubectl Commands - K8s CLI**
    
    * Create and Debug Pod in a Minicluster
        
* **Kubernetes YAML Configuration File**
    
* **Demo Project: MongoDB and MongoExpress**
    
* **Organizing Your Components with K8s Namespaces**
    
* **Kubernetes Service Types**
    
* **Making Your App Accessible from Outside with Kubernetes Ingress**
    
* **Persisting Data in Kubernetes with Volumes**
    
    * Persistent Volume, Persistent Volume Claim, Storage Class
        
* **ConfigMap and Secret Kubernetes Volume Types**
    
* **Deploying Stateful Apps with StatefulSet**
    
* **Deploying Kubernetes Cluster on a Managed Kubernetes Service (K8s on Cloud)**
    
* **Helm - Package Manager of Kubernetes**
    
* **Helm Demo: Install a Stateful Application on Kubernetes Using Helm**
    
* **Demo: Deploy App from Private Docker Registry**
    
* **Extending the Kubernetes API with Operator**
    
* **Secure Your Cluster - Authorization with Role-Based Access Control (RBAC)**
    

### Microservices in Kubernetes

* **Introduction to Microservices**
    
* **Demo Project: Deploy Microservices Application**
    
* **Demo Project: Create Common Helm Chart for Microservices**
    
* **Demo Project: Deploy Microservices with Helmfile**
    
* **Production & Security Best Practices**
    

### AWS & Kubernetes

* **AWS Container Services: Overview (ECR, ECS, EKS, Fargate)**
    
* **Create an EKS Cluster with AWS Management Console (UI)**
    
    * Create Cluster VPC, Cluster Roles
        
    * Use CloudFormation Stack
        
    * EC2 Worker Nodes
        
    * Configure Kube Context to Connect to the Cluster
        
* **Configure Autoscaling in EKS Cluster**
    
* **Create Fargate Profile for EKS Cluster**
    
* **Create an EKS Cluster with eksctl (the Easy Way)**
    

### AWS & Kubernetes & Jenkins & Docker

* CI/CD
    
* **Configure kubectl Inside Jenkins**
    
* **Configure Kube Context in Jenkins**
    
* **Install aws-iam-authenticator in Jenkins**
    
* **Complete Jenkins Pipeline - Deploy to EKS Using** `kubectl`
    
* **Complete Jenkins Pipeline - Build and Push Docker Image to ECR and Deploy to EKS**
    
* **Complete Jenkins Pipeline - Deploy to LKE Using Kubernetes CLI Plugin and Kubeconfig File**
    

## Lesson 20: Introduction to Terraform

* **What is Terraform? How it Works**
    
* **Terraform Architecture**
    
* **Install Terraform & Setup Terraform Project**
    
* **Providers in Terraform**
    
* **Resources & Data Sources**
    
* **Change & Destroy Terraform Resources**
    
* **Terraform Commands**
    
* **Terraform State**
    
* **Output Values**
    
* **Variables in Terraform**
    
* **Environment Variables in Terraform**
    
* **Create Git Repository for Local Terraform Project**
    

### Terraform & AWS

* **Automate Provisioning EC2 Server with Terraform**
    
* **Provisioners in Terraform**
    
* **Modularize the Demo Project**
    

### Terraform & AWS & Kubernetes

* **Automate Provisioning EKS Cluster with Terraform**
    
    * Use Existing Modules from Terraform Registry
        
    * Create VPC
        
    * Provision EKS Cluster
        

### Terraform & AWS & Jenkins - Complete CI/CD

* **Complete CI/CD with Terraform**
    
    * Configure Terraform in Jenkins
        
    * Automate Provisioning EC2 Instance from Jenkins Pipeline and Deploy the Application with Docker-Compose
        
* **Remote State in Terraform**
    
* **Terraform Best Practices**
    

## Lesson 21: Core Concepts and Syntax of Ansible

* **Introduction to Ansible**
    
* **Install & Configure Ansible**
    
* **Setup Managed Server to Configure with Ansible**
    
* **Ansible Inventory**
    
* **Ansible Ad-Hoc Commands**
    
* **Configure AWS EC2 Server with Ansible**
    
* **Managing Host Key Checking and SSH Keys**
    
* **Ansible Tasks, Play & Playbook**
    
* **Ansible Modules**
    
* **Ansible Collections & Ansible Galaxy**
    
* **Ansible Variables - Make Your Playbook Customizable**
    
* **Troubleshooting in Ansible**
    
* **Conditionals**
    
* **Privilege Escalation**
    
* **Ansible Configuration - Default Inventory File**
    

### Learn Most Common Ansible Modules with Hands-On Demos

* **Project: Deploy Node.js Application**
    
* **Project: Deploy Nexus**
    
* **Configure Servers with Different Linux Distributions on AWS and Digital Ocean Platforms**
    
    * Install Tools on a Server, Configure Applications, Work with a File System, Move Static Files Between Machines, etc.
        
    * Map and Translate Shell Scripts and Commands into Ansible Playbooks to Automate Various Common Tasks
        

### More Advanced Topics & Integrations with Other Technologies

* **Dynamic Inventory for EC2 Servers**
    
* **Ansible Roles - Make Your Ansible Content More Reusable and Modular for Better Maintenance**
    
* **Project: Ansible & Terraform**
    
* **Project: Run Docker Applications**
    
* **Project: Deploying Applications in Kubernetes**
    
* **Project: Run Ansible from Jenkins Pipeline**