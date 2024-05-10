---
title: "All About Argo CD, A Beginner's Guide"
datePublished: Fri May 10 2024 05:49:59 GMT+0000 (Coordinated Universal Time)
cuid: clw09cwrp000c08js1hhcft1d
slug: all-about-argo-cd-a-beginners-guide

---


ArgoCD, being one of their 1st in the market known for having a declarative GitOps based deployment over Kubernetes is one of the most adopted Continuous Delivery tool. It has been known for its excellent application deployment and management over Kubernetes and features such as auto healing clusters, user-access management, status check, etc. It is [open-sourced on GitHub](https://github.com/argoproj/argo-cd) under Apache 2.0 License.

# ArgoCD Existence, Why 🤔?

[![but-why](https://res.cloudinary.com/practicaldev/image/fetch/s--znpQN1v---/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ec6gjcpw7vvlrkj88cvs.jpeg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--znpQN1v---/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ec6gjcpw7vvlrkj88cvs.jpeg)

  
There are already hell lots of tools in the market, so why do we need another one? To justify the existence of ArgoCD, let's try to understand the workflow for application deployment before-and-after ArgoCD.

## Workflow Before ArgoCD

[![before-argocd](https://res.cloudinary.com/practicaldev/image/fetch/s--mIrM_-vr--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f9dxi44lpvq97pkg03al.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--mIrM_-vr--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/f9dxi44lpvq97pkg03al.jpg)

Before the existence of ArgoCD, the pipeline seems something like the image above. A common ci-cd tool is used for both the Continuous Integration and Continuous Deployment.

* once the code is being pushed to version-control let's say GitHub, the tool triggers the other jobs
    
* it runs the test-cases, build images, push the image to respective container registry
    
* then changes the deployment manifests as per the new image build, and then deploy the new manifest using `kubectl` commands
    

All these jobs/tasks are being performed by a ci-cd tool. This is how traditional ci-cd workflow works before the existence of ArgoCD. However there are some challenges in this workflow.

* We need to install and configure tools like kubectl, helm, etc in the ci-cd tools
    
* We will have to provide access to k8s cluster and cloud providers if using managed services like eks to the respective ci-cd tool
    
* It may lead to security loopholes as credentials are provided to external tools
    
* There's no visibility of deployment metrics, your ci-cd tools doesn't know the status of deployed application once they apply the manifests
    

## Workflow After ArgoCD

[![after-argocd](https://res.cloudinary.com/practicaldev/image/fetch/s--SlS9e6iJ--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/j6pnk2lfu0hixq09avgj.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--SlS9e6iJ--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/j6pnk2lfu0hixq09avgj.jpg)

After the ArgoCD was launched in the market, the complete workflow has been changed. As you can see in the image, the Continuous Integration and Continuous Deployment has been separated now. ArgoCD uses declarative GitOps based deployment which states that the best practices is to have two different git repositories, one for application source code and another for deployment manifest files.

* once the code has been pushed to version, the CI pipeline trigger the job
    
* starts to run test cases, build images, push images to respective container registry and then update the manifest according and push manifests to its respective git repository
    
* once the updated manifests is pushed to its respective repository be it GitHub, Gitlab, etc as shown in the image, ArgoCD installed within the cluster automatically checks for the updates and apply within the cluster.
    

This is how, the respective ci-cd tool is limited to CI and ArgoCD handles the CD part and thus separating both the operations. There are many different advantages of using this workflow, some of them are -

* it uses git as a single source of truth, thus incorporating GitOps principles for the deployment
    
* since ArgoCD is installed within the cluster and is the only one that makes changes within the cluster, it doesn't require any extra credentials unlike the case of a ci-cd tool
    
* ArgoCD provides a dashboard to manage all the deployed applications hence enables you to get the status of application being deployed or not which we doesn't get in case of previous workflow
    
* easy rollback, as the cluster is synced with a separate git repository so we just need to revert the changes in git and the cluster will be automatically synced with the git repository
    
* disaster recovery, as in case of any disaster you just need to point the git repository to the newly created cluster and it will have all the configurations of the previous cluster
    

So, these are some of the major advantages of the Workflow after ArgoCD. Now let's dive into ArgoCD and do some practical stuffs.

# ArgoCD Getting Started

As we have seen some background concepts of ArgoCD and its need, let dive into some hands-on part. There are two different ways to install and setup ArgoCD in you cluster,

1. Install using script
    
2. Install using helm chart
    

Let's look into each of these.

**\[Note: kubectl command must be installed and kubeconfig file should be at the default location(~/.kube/config) before installing argocd\]**

## Installation by script

Just with few commands you can have your ArgoCD installed in your cluster and ready to deploy an application over it. Please execute the below commands for installation -

Create a namespace `argocd` where all ArgoCD resources will be installed

```bash
kubectl create namespace argocd
```

Install all resources in the created namespace

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

After installation, you need to access the dashboard. There are different methods given in their [documentation](https://argo-cd.readthedocs.io/en/stable/getting_started/#3-access-the-argo-cd-api-server) for accessing the dashboard. We will be using port-forward as we are installing in our local machine. Please execute the command below

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Now your ArgoCD dashboard can be accessed in `127.0.0.1:8080` as you can see in the image below.

[![argocd-dashboard](https://res.cloudinary.com/practicaldev/image/fetch/s--lEu5-bhW--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nofuzua4039l96mekfna.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--lEu5-bhW--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nofuzua4039l96mekfna.png)

For the credentials to login, the username is `admin` and for password, execute the following command -

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

Congratulation 🥳 You have successfully logged into the argocd dashboard.  
Now, this was one of the method. It can also be installed using helm chart. Let's see how.

## Installation by helm

Recently argo-project has launched their official helm-chart support for ArgoCD, which enables us to install it with helm as well. Please execute the following command to install ArgoCD with helm -

Add the helm repository in your system

```bash
helm repo add argo https://argoproj.github.io/argo-helm
```

Now install the ArgoCD helm chart

```bash
helm install my-release argo/argo-cd
```

The advantage of installing with helm chart is that, you can easily provide the configuration as you want during the installation. For details of the parameters support by ArgoCD helm chart, please have a look at this detailed [README](https://github.com/argoproj/argo-helm/tree/master/charts/argo-cd#general-parameters)

After installation, to access the dashboard and credentials, you can follow the same commands as we did earlier.

**\[Note: Make sure to remove namespace i.e,** `-n argocd` if you have not provided any namespace during the installation from commands to access dashboard & credentials. To provide the namespace, append this with helm install command `--create-namespace --namespace argocd`\]

This is how easily you can install ArgoCD with the two different methods. For detailed documentation of getting started with ArgoCD, please have a [look at this](https://argo-cd.readthedocs.io/en/stable/getting_started/#getting-started). Now, lets deploy a simple application and configure it to manage by ArgoCD.

# Application Deployment

For any application to be deployed and managed by ArgoCD, we need to create a config file say, `application.yaml` which will have all the configurations required by ArgoCD containing the repository URL to sync with, Path where all manifests are being stored which needs to be deployed, namespace, and other configs. Here's a [demo project](https://github.com/Abhinav-26/ArgoCD-Config-Test) which we will deploy in our cluster having all `yamls` and `application.yaml` file with bare minimum configs.

Let's deploy our application. Please follow along with the following steps.

* First, we need to store all the config files, including the `application.yaml` in a separate GitHub (GitLab, bitbucket, etc) repository as you [can see here](https://github.com/Abhinav-26/ArgoCD-Config-Test)
    
* Then we just need to deploy the `application.yaml` which consists config required by ArgoCD in the cluster by using the following command -
    

```bash
kubectl apply -f application.yaml
```

[![kubectl-apply](https://res.cloudinary.com/practicaldev/image/fetch/s--Nkp3HXNG--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jctvbkokfrlqazr975ho.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--Nkp3HXNG--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jctvbkokfrlqazr975ho.png)

Now only just by applying the ArgoCD application config file, all other k8s yamls will automatically gets deployed and synced with the cluster. In the below image you can see that, the application, `go-app-argo-config` is responsible for creating all other resources.

[![argo-config](https://res.cloudinary.com/practicaldev/image/fetch/s--ocu67w-u--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/brglesoh6gl1155uaifw.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--ocu67w-u--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/brglesoh6gl1155uaifw.png)

If we want to update the deployment, service or add any other k8s manifests (yamls), we simply need to makes the changes and push in the GitHub repository synced with it and rest will be taken care ArgoCD.

So, this was all about ArgoCD which you need to kick-start and play around it. If you have any doubts or suggestions, please feel free to comment it down, I would be happy enough to answer all your queries.

For more details about ArgoCD please feel free to check out their [Github Repository](https://github.com/argoproj/argo-cd/)