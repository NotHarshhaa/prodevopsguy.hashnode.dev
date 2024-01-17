---
title: "Deployment of Super Mario on Kubernetes using Terraform"
datePublished: Wed Jan 17 2024 05:50:11 GMT+0000 (Coordinated Universal Time)
cuid: clrhd61r7000f09la8iyr9v8x
slug: deployment-of-super-mario-on-kubernetes-using-terraform
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705469503053/0493dc69-1eab-4412-8e9c-3c9bdc461bb7.gif
tags: aws, kubernetes, devops, terraform, super-mario

---

**Super Mario the game which we will never forget so today we are going to deployed it on EKS using Terraform via AWS EC2**

## **Prerequisite →**

1. **Only thing that you need is the AWS account and also you need to know some basics of it**
    
2. Than we configure Terraform inside an ec2 instance
    
3. we also need an IAM ec2 role that provide necessary permission to ec2
    

## **Completion steps →**

**Step 1 →** Login and basics setup

**Step 2 →** Setup Docker ,Terraform ,aws cli , and Kubectl

**Step 3 →** IAM Role for EC2

**Step 4 →**Attach IAM role with your EC2

**Step 5 →** Building Infrastructure Using terraform

**Step 6 →** Creation of deployment and service for EKS

**Step 7 →** Destroy all the Infrastructure

## **Let’s do it**

## **Step 1 → Login and basics setup**

1. login into your aws account as a **root user**
    

![](https://miro.medium.com/v2/resize:fit:431/1*SD9pNUxx4Zcoob_RQ7p3sg.png align="left")

**2\. Launch an EC2 instance with the following setting**

![](https://miro.medium.com/v2/resize:fit:505/1*aPkgzkKa3yb2Yde27_4vEg.png align="left")

![](https://miro.medium.com/v2/resize:fit:2020/1*8qh8uM83Cnr6jb2uBMB-UA.png align="left")

![](https://miro.medium.com/v2/resize:fit:2020/1*_viDWdD3cEJ7jDfTaPb7cg.png align="left")

![](https://miro.medium.com/v2/resize:fit:2020/1*MKkjnn7dEm09ZJ9pXCFXvw.png align="left")

allow https,http and set a key pair

**3\. Click on launch Instance**

![](https://miro.medium.com/v2/resize:fit:736/1*EQzQremJHk551pahlcgOyg.png align="left")

![](https://miro.medium.com/v2/resize:fit:736/1*mwTiumL5uyL2fbVR2VkASw.png align="left")

click on connect on the top right corner

4\. click on connect and **you are connected with your machine**

![](https://miro.medium.com/v2/resize:fit:2020/1*r4mSqDFXksHvLfjZDuQDKA.png align="left")

![](https://miro.medium.com/v2/resize:fit:2020/1*xrCcASRjvK4WJrAaB2D5LQ.png align="left")

**5\. run the following commands**

**a. sudo su**

**b. apt update -y**

## **Step 2 → Setup Docker ,Terraform ,AWS cli , and Kubectl**

### **Setup Docker →** [**click on me to know basics of docker**](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)

1. **apt install** [**docker.io**](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)
    

![](https://miro.medium.com/v2/resize:fit:706/1*4mVLNA5Eks5WY69djQoAHQ.png align="left")

2\. **usermod -aG docker $USER** # Replace with your username e.g ‘ubuntu’

3\. **newgrp docker**

### **Setup Terraform →** [**click on me to know basics of terraform**](https://medium.com/@aakibkhan1/terraform-infrastructure-building-tool-1a8a5ab27800)

1. sudo apt install wget -y
    
2. wget -O- [https://apt.releases.hashicorp.com/gpg](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd) | sudo gpg — dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg  
    echo “deb \[signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg\] [https://apt.releases.hashicorp.com](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd) $(lsb\_release -cs) main” | sudo tee /etc/apt/sources.list.d/hashicorp.list
    
3. sudo apt update && sudo apt install terraform -y
    

![](https://miro.medium.com/v2/resize:fit:612/1*a39ZL8T0HmllRJVB8yfEPw.png align="left")

### **Setup AWS cli**

Aws using your computer’s command lines instead of clicking around on a website. It helps you do things like telling AWS to create or manage stuff, all by typing commands in a special language your computer understands. It’s like giving orders to AWS with your keyboard instead of a mouse.

1. curl “[https://awscli.amazonaws.com/awscli-exe-linux-x86\_64.zip](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)" -o “[awscliv2.zip](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)”
    
2. sudo apt-get install unzip -y
    
3. unzip [awscliv2.zip](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)
    
4. sudo ./aws/install
    

### **Setup kubectl →** [**click on me to know basics of**](https://medium.com/@aakibkhan1/kubernetes-part-2-the-architecture-part-e06c0221b7a) **Kubernetes**

1. sudo apt install curl -y
    
2. curl -LO [https://dl.k8s.io/release/$(curl](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd) -L -s [https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)
    
3. sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
    

![](https://miro.medium.com/v2/resize:fit:997/1*rPhWw--gtp9i0kxUJxCSCg.png align="left")

![](https://miro.medium.com/v2/resize:fit:743/1*zgVICCIh7qNm2Gct1Kw-3Q.png align="left")

**Every thing is setup and installed let’s make a IAM EC2 Role**

## **Step 3 → IAM Role for EC2**

**Why we need IAM role for EC2 →** It is used by your ec2 instance to create EKS cluster and manage s3 bucket by applying this IAM role it gives the authenticity to your ec2 to do changes in aws account

1. on the search bar type IAM
    

![](https://miro.medium.com/v2/resize:fit:736/1*g5QpX_Fvz0iTSRTVnFNdSg.png align="left")

2\. click on Roles on the left side

![](https://miro.medium.com/v2/resize:fit:261/1*SrU78t_QY42pPMPPkWuNLQ.png align="left")

3\. click on create role and choose EC2 from the dropdown

![](https://miro.medium.com/v2/resize:fit:736/1*6B_OA0fdXlJP1B8R_EvEhg.png align="left")

4\. click on next

5\. choose **administrator access** on permission sections

![](https://miro.medium.com/v2/resize:fit:736/1*aZR8LnKKaw4Ze52gnb-m7Q.png align="left")

6\. click on next and give a name to your role

![](https://miro.medium.com/v2/resize:fit:736/1*QvP0IbgpWb6fXL7aS7bQqw.png align="left")

7\. click on **create role option** and your IAM role is created

## **Step 4 →Attach IAM role with your EC2**

1. go to EC2 section
    
2. click on actions → security → modify IAM role option
    

![](https://miro.medium.com/v2/resize:fit:736/1*BZMX9pqcfI-zYbcDFjhkEg.png align="left")

3\. choose the role from dropdown and click on update IAM role

![](https://miro.medium.com/v2/resize:fit:736/1*aMSd0h6_3i_pKb6JYidATg.png align="left")

### **why we need IAM Role →**

Imagine you have a robot (EC2 instance) that does tasks for you in a big factory (AWS environment). Now, this robot needs to access different rooms (AWS services like S3, DynamoDB, etc.) to perform its tasks.

Here’s where IAM (Identity and Access Management) comes in:

1. **Robot Needs a Key to Enter Rooms:** The IAM Role is like giving your robot a special key. This key allows the robot to enter specific rooms (access certain AWS services). Without this key, the robot can’t get in.
    
2. **Different Keys for Different Robots:** Each robot (EC2 instance) can have its own key (IAM Role) with specific permissions. So, one robot may have a key to enter the storage room (access S3), while another robot has a key to enter the database room (access DynamoDB).
    
3. **No Need for Hardcoding Passwords:** Using IAM Roles means you don’t have to hardcode passwords (access credentials) into the robot. It’s like not writing down passwords on the robot itself. The robot just uses its key when needed.
    
4. **Easily Change Permissions:** If you want to change what a robot can do, you just change the permissions on its key (IAM Role). No need to reprogram the robot or give it a new password; just update the permissions on its key.
    
5. **Secure and Controlled Access:** IAM Roles help keep things secure. You can control exactly what each robot is allowed to do. This way, if one robot is compromised or needs a different role, you can easily adjust its permissions without affecting others.
    

**Now everything is done what we have to do is just throw and some commands and build our infrastructure using terraform to run super mario**

## **Step 5 → Building Infrastructure Using terraform**

1. Clone the GitHub repo by →
    

a. mkdir super\_mario

b. cd super\_mario

**c. git clone** [https://github.com/NotHarshhaa/Deployment-of-super-Mario-on-Kubernetes-using-terraform.git](https://github.com/NotHarshhaa/Deployment-of-super-Mario-on-Kubernetes-using-terraform.git)

![](https://miro.medium.com/v2/resize:fit:666/1*0EeFxDt4gsmgCEKmcGe8wA.png align="left")

d. cd Deployment-of-super-Mario-on-Kubernetes-using-terraform/

![](https://miro.medium.com/v2/resize:fit:736/1*ngTfbXTY9-868Q2jhn5DAA.png align="left")

**e. cd EKS-TF**

![](https://miro.medium.com/v2/resize:fit:736/1*xxoxB8NuPH67ml2x7VNpnA.png align="left")

f. edit the [backend.tf](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd) file by → **vim** [**backend.tf**](https://medium.com/@aakibkhan1/docker-part-2-architecture-and-commands-f286a516d8dd)

![](https://miro.medium.com/v2/resize:fit:736/1*NgK_kz_ktgIqmEeOqcHiEA.png align="left")

**Note →make sure to provide your bucket and region name in this file otherwise it doesn’t work and IAM role is also associated with your ec2 which helps ec2 to use other services such S3 bucket**

**NOW RUN →**

1. **terraform init**
    

![](https://miro.medium.com/v2/resize:fit:736/1*lRVvW6ZWAH4utl7a1dAiTA.png align="left")

When we run terraform init, it sets up your working area, downloads necessary plugins, and makes sure everything is in place so that you can start using Terraform to create, update, or manage your infrastructure. It's like getting all the tools and materials ready before you start building something amazing with your computer.

**2\. terraform validate**

![](https://miro.medium.com/v2/resize:fit:736/1*HKVC08bwyzMSAlk9g1WAbw.png align="left")

Terraform validate reviews our code to catch any syntax errors or mistake and gives an output **success** if everything is no error in the file

**3\. terraform plan**

![](https://miro.medium.com/v2/resize:fit:1052/1*lcDJ6nVtJCvlysqYnGo9MA.png align="left")

**Terraform plan** is used to see what changes will be made to your infrastructure. By using this command we could review and confirm that everything looks good before giving the final approval to build or modify our application infrasructure It is like the blueprint of the construction project before actually creating or changing anything with Terraform

**4\. terraform apply**

```bash
terraform apply --auto-approve
```

Running `terraform apply --auto-approve` is like telling computer, "Go ahead and build everything exactly as planned without asking me for confirmation each time." It's a way to automate the deployment of your infrastructure without needing our constant input. When we execute this command, Terraform reads our code, figures out what needs to be created or changed, and then goes ahead with the construction, skipping the usual step where it checks with you for approval.

![](https://miro.medium.com/v2/resize:fit:736/1*DNJZqQWbl7cY10wFFKL4eg.png align="left")

**It takes your 5 to 10 min for completion**

5\. Below command is used to update the configuration of EKS

```bash
aws eks update-kubeconfig --name EKS_CLOUD --region us-east-1
```

The command `aws eks update-kubeconfig --name EKS_CLOUD --region us-east-1` is like telling our computer, "Hey, I'm using Amazon EKS (Elastic Kubernetes Service) in the 'us-east-1' region, and I want to connect to it. you could use your desired location

![](https://miro.medium.com/v2/resize:fit:736/1*rfx-NuPhkfYq9SaNuVCC5Q.png align="left")

## **Step 6 → Creation of deployment and service for EKS**

1. change the directory where deployment and service files are stored use the command → **cd ..**
    
2. create the deployment
    

```bash
kubectl apply -f deployment.yaml 
```

![](https://miro.medium.com/v2/resize:fit:736/1*t8aqOnITzqQHOaISIFEzBA.png align="left")

`deployment.yaml` file is like a set of instructions that tells a computer system, "Hey, here's how you should run and manage a particular application " . It provides the necessary information for a computer system to deploy and manage a specific software application. It includes details like what the application is, how many copies of it should run, and other settings that help the system understand how to keep the application up and running smoothly.

3\. Now create the service

```bash
kubectl apply -f service.yaml
```

![](https://miro.medium.com/v2/resize:fit:736/1*VwtxCk0WbtcMSZ-zM92pNA.png align="left")

`service.yaml` file is like a set of rules that helps computers find and talk to each other within a software application. It's like a directory that says, "Hey, this is how you can reach different parts of our application." It specifies how different parts of your application communicate and how other services or users can connect to them.

4\. run → kubectl get all

![](https://miro.medium.com/v2/resize:fit:736/1*G71bvARwkLUZ4Pg0du8-tA.png align="left")

5\. now Run the following command to get the load balancer ingress

**This command tells all the details of your application**

```bash
kubectl describe service mario-service
```

![](https://miro.medium.com/v2/resize:fit:736/1*UJ7RQenEx5WRznLcW6AhsQ.png align="left")

copy the load balancer ingress and paste it on browser and your game is running

![](https://miro.medium.com/v2/resize:fit:736/1*5hhg0MIBkWRRZqMRydPhZQ.png align="left")

**Play and Enjoy but don’t forget to destroy everything that’s saves of aws bill and you aws account too**

### **Load Balancer Ingress →**

It is a mechanism that helps distribute incoming internet traffic among multiple servers or services, ensuring efficient and reliable delivery of requests.

It’s like having a receptionist at a busy office building entrance who guides visitors to different floors or departments, preventing overcrowding at any one location. In the digital world, a Load Balancer Ingress helps maintain a smooth user experience, improves application performance, and ensures that no single server becomes overwhelmed with too much traffic.

## **Step 7 → Destroy all the Infrastructure**

1 . Below commands delete your deployment and service

```bash
kubectl delete service mario-service
```

```bash
kubectl delete deployment mario-deployment
```

![](https://miro.medium.com/v2/resize:fit:736/1*TlTt41OqrXH1-eNc6yXlMQ.png align="left")

2\. After service and deployment destruction let’s destroy the infrastructure by the following command it will delete your EKS cluster

```bash
cd EKS-TF
terraform destroy --auto-approve
```

**after 3 -5 mins all things are destroyed**

![](https://miro.medium.com/v2/resize:fit:736/1*v6RLAgzh3JaPtjX7Mkd66w.png align="left")

3\. Now go to your EC2 and terminate your Instance

## **This is all about this Project see you in the next one :)**