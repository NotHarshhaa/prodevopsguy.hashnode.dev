---
title: "🔥5 Must have tools to install on your Kubernetes cluster ✨️🚀"
datePublished: Wed Nov 29 2023 07:56:11 GMT+0000 (Coordinated Universal Time)
cuid: clpjh3cjq001j09ig1tju9jfn
slug: 5-must-have-tools-to-install-on-your-kubernetes-cluster
tags: cloud, tools, kubernetes, devops, ci-cd

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701244252060/39e9fe27-d7cc-4fe6-a8f4-127c65fcb080.webp align="center")

This article lists five must-have tools for developers to install on their Kubernetes cluster. 🎉

Feel free to explore these projects, star the repositories, and contribute to your favourites. 😉

***Without any further ado, let's get started. 🏃‍♂️💨***

![Let's start](https://res.cloudinary.com/practicaldev/image/fetch/s--XyW3-Qn5--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1p4nkxc6qnkbcpo59q9c.gif align="left")

---

## **1\.** [**Odigos**](https://odigos.io/)

> 💡 Distributed tracing without code changes.

[![Odigos - Observability control plane](https://res.cloudinary.com/practicaldev/image/fetch/s--5kOcelDS--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://res.cloudinary.com/practicaldev/image/fetch/s--vrtvOUOw--/c_limit%252Cf_auto%252Cfl_progressive%252Cq_auto%252Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/najz95vmowa4uv1jlecq.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--vrtvOUOw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/najz95vmowa4uv1jlecq.jpg)

Odigos is an open-source observability control plane that enables organizations to create and maintain their observability pipeline.

Odigos automatically generates telemetry data in OpenTelemetry format to any Observability backend, without any code change. 😻.

It automatically instruments our application, eliminating the need to set up OpenTelemetry or anything on our own. Odigos handles it all. 🤯

All this is possible because of the following:

* **Automated Instrumentation 👾:** Odigos enables automated instrumentation of applications with OpenTelemetry and eBPF, eliminating the need for code modifications.
    
* **Universal Observability Tool Compatibility 🤝:** It smoothly integrates with various observability tools, providing comprehensive support and efficient collector management.
    

> We've recently published an article on implementing Odigos, check it out [here](https://dev.to/odigos/how-to-monitor-your-requests-between-multiple-applications-4fi8).

[🌟 Star Odigos](https://github.com/keyval-dev/odigos)

---

## **2\.** [**Argo CD**](https://argoproj.github.io/cd/)

> 💡 Declarative GitOps CD for Kubernetes.

[![Argo CD Working](https://res.cloudinary.com/practicaldev/image/fetch/s--km0Wpn9j--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://res.cloudinary.com/practicaldev/image/fetch/s--Q6PXSe2d--/c_limit%252Cf_auto%252Cfl_progressive%252Cq_auto%252Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oawy0bzp0hok5jvwq1l3.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--Q6PXSe2d--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oawy0bzp0hok5jvwq1l3.jpg)

Argo CD is a powerful GitOps CD tool that can help automate and simplify the deployment and management of Kubernetes applications 🚀.

Argo CD main features include a web UI 💻, CLI, rollback capabilities, and simplified monitoring.

> **Why use Argo CD over traditional CD tools?** 🤔

* **Git as a single source of truth 🤫:** Argo CD uses Git as a single source of truth for app and infrastructure configuration. It makes it easy to track changes and roll back deployment if something goes wrong.
    
* **Friendly web UI 💻:** Argo CD provides a dashboard to manage and get the status of all the deployed applications.
    
* **Easy Rollbacks 🔄:** The cluster is synced with a separate git repository so we just need to revert the changes in git and the cluster will be automatically synced with the git repository.
    
* **Disaster Recovery 🌋:** In case of a disaster just point the git repository to the newly created cluster and it will have all the configs of the previous cluster.
    

These features make it accessible for both beginners and experienced Kubernetes users.

> In short, Argo CD is a GitOps CD tool for Kubernetes ☸️ that uses Git as the single source for app and infrastructure configurations and provides easy rollbacks, dashboard, and disaster recovery capabilities.

[🌟 Argo CD on GitHub](https://github.com/argoproj/argo-cd)

---

## **3\.** [**Nginx Ingress Controller**](https://docs.nginx.com/nginx-ingress-controller/)

> 💡 Specialized load balancer for Kubernetes environments.

[![Nginx Ingress Controller Working](https://res.cloudinary.com/practicaldev/image/fetch/s---SBCG0mD--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://res.cloudinary.com/practicaldev/image/fetch/s--kF0dD7J1--/c_limit%252Cf_auto%252Cfl_progressive%252Cq_auto%252Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/muuooo0w51619q33djhf.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--kF0dD7J1--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/muuooo0w51619q33djhf.jpg)

It is the most widely used ingress controller for Kubernetes. ☸️ It uses Nginx as a reverse proxy and load balancer.

It runs 🏃‍♂️ in a Kubernetes environment with Nginx Plus or Nginx Open Source instances.

The key responsibilities of the Nginx Ingress Controller are 👇:

* Load balance traffic to containers 📦 in the Kubernetes cluster. It monitors Kubernetes ingress resources and routes traffic to the appropriate Kubernetes services and pods.
    
* Handles networking, traffic management 👮‍♂️, communication and security 🔒.
    
* Deploys resources based on its configuration 📝 and automatically updates rules based on ingress resource definitions.
    

> In short, It manages traffic, and security and dynamically adjusts routing based on Kubernetes ingress resources and configurations.

[🌟 Nginx Ingress Controller on GitHub](https://github.com/kubernetes/ingress-nginx)

---

## **4\.** [**AWS Controller for Kubernetes**](https://aws-controllers-k8s.github.io/community/)

> 💡 Manage AWS services using Kubernetes.

[![AWS Controllers for Kubernetes](https://res.cloudinary.com/practicaldev/image/fetch/s--Z7it4Zr7--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://res.cloudinary.com/practicaldev/image/fetch/s--e5ctsHl5--/c_limit%252Cf_auto%252Cfl_progressive%252Cq_auto%252Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o4ingv6dcfvzyyq20ps6.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--e5ctsHl5--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o4ingv6dcfvzyyq20ps6.jpg)

**ACK**, short for AWS Controllers for Kubernetes, is a set of custom controllers enabling integration between AWS services and Kubernetes clusters that let you directly manage AWS services from Kubernetes 😮.

ACK makes it simple to build scalable and highly available Kubernetes applications that utilize AWS services. It provides a unified way to manage our application and its dependencies ✨️.

Some key features of AWS Controllers for Kubernetes are:

* Define and use AWS service resources directly from Kubernetes.
    
* Take advantage of AWS-managed services for our Kubernetes applications without needing to define resources outside of the cluster or run services that provide supporting capabilities like databases 🗄 or message queues.
    

> In short, ACK enables us to manage AWS services directly from Kubernetes and provides a unified way to define and use AWS services from within our Kubernetes cluster.

[🌟 AWS Controllers for K8 on GitHub](https://github.com/aws-controllers-k8s/community)

---

## **5\.** [**Kyverno**](https://kyverno.io/)

> 💡 Policy engine designed for Kubernetes.

[![Kyverno - K8S policy engine](https://res.cloudinary.com/practicaldev/image/fetch/s--HjuT3IsS--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://res.cloudinary.com/practicaldev/image/fetch/s--DvZZ-qz5--/c_limit%252Cf_auto%252Cfl_progressive%252Cq_auto%252Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uf6a4ut913qf4trvjmhu.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--DvZZ-qz5--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uf6a4ut913qf4trvjmhu.jpg)

When deploying things in Kubernetes, like Pods or ConfigMaps, it's important to set rules/policies.

A key practice is avoiding the use of the `latest` tag for container images in production, as it's often a work-in-progress dev build.

> **What does Kyverno do?** 🧐

In Kubernetes, the security issue is a big deal, and one of the main reasons is **misconfigurations**. These security issues arise when there are no good rules (policies) in place.

This is where a policy manager like **Kyverno** comes into action. 😎

> 🚨 **NOTE:** Kyverno does not work on any other environment other than Kubernetes. If you are looking for a policy management that is vendor agnostic you might consider using something like [Open Policy Agent](https://www.openpolicyagent.org/).

Kyverno manages policies, whether they're about security or just good practices, in our Kubernetes setup.

We can create rules for things like the `latest` tag issue mentioned earlier or focus on security, like making sure your container images are safe in the software supply chain.

> In short, Kyverno is a policy engine that helps manage security and best practices by allowing users to manage policies for deployments, addressing issues like misconfigurations and promoting good practices ✅️.

[🌟 Kyverno on GitHub](https://github.com/kyverno/kyverno)

---

> If you think of any other helpful projects that I haven't covered in this article, please share them in the comments section below. 👇🏻

So, that is it for this article. Thank you so much for reading! 🎉