---
title: "Basic DevOps CI-CD workflow!"
datePublished: Tue May 21 2024 10:21:31 GMT+0000 (Coordinated Universal Time)
cuid: clwg8wglj000t0al86nna3zoj
slug: basic-devops-ci-cd-workflow
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1716285484160/7828e31a-36bc-4923-a49a-d03eddf4e1c1.jpeg
tags: docker, github, workflow, kubernetes, developer, monitoring, devops, jenkins, ci-cd, devops-articles

---

## Basic DevOps CI-CD workflow steps!

1. **Developer Writes Code**: The developer writes the application code which is then pushed to a version control system, such as Git.
    
2. **Source Code (Git)**: The code is stored and managed in a Git repository (for e.g.: GitHub, Bit Bucket, Gitlab etc.). This repository tracks changes, allows for version control, and facilitates collaboration among team members.
    
3. **Creates Dockerfile**: The developer creates a Dockerfile in the repository. This Dockerfile contains instructions on how to build a Docker image for the application.
    
4. **Docker Builds Image**: Docker reads the Dockerfile and builds a Docker image based on the instructions provided.
    
5. **Docker Image**: The resulting Docker image is a portable, standalone package of the application. This image can be shared and deployed on any system that supports Docker.
    
6. **Pushes to Container Registry**: The Docker image is pushed to a container registry, such as Docker Hub/ Jfrog Artifactory etc. The registry acts as a central repository for Docker images, making them accessible for deployment.
    
7. **Pulls from CI/CD Tool**: Make use of any CI-CD tool (for eg: Jenkins), pulls the Docker image from Docker Hub. Jenkins automates the deployment pipeline, ensuring the latest image is used for deployment.
    
8. **Deploys to Kubernetes Cluster**: CD tool deploys the Docker image to a Kubernetes cluster. Kubernetes orchestrates the deployment, scaling, and management of containerized applications.
    
9. **Runs Containers (Kubernetes Pods)**: The Docker image runs within Kubernetes Pods. Pods are the smallest deployable units in Kubernetes, containing one or more containers.
    
10. **Monitoring**: Make use of a monitoring tool(for eg: Prometheus), collects and stores metrics from the running containers. It monitors the health and performance of the application and the Kubernetes cluster.
    
11. **Visualizes with Grafana**: Grafana, a data visualization tool, accesses the metrics stored by Prometheus. It provides dashboards and visualizations to help analyze the application's performance.
    
12. **Alerts via Alert Manager**: Alert Manager, integrated with Prometheus, processes alerts based on predefined conditions. Alert Manager sends notifications to the development or operations team via various channels such as email or Slack.
    

---

***Thank you for reading my blog …:)***

© **Copyrights:** [ProDevOpsGuy](https://t.me/prodevopsguy)

## Support 🫶

* Help spread the word about **ProDevOpsGuy** by sharing it on social media and recommending it to your friends. 🗣️
    
* You can also sponsor 🏅 on [GitHub Sponsors](https://github.com/sponsors/NotHarshhaa) // 🎗️ [Support Our Work](https://prodevopsguy.site/support-us) 🎗️