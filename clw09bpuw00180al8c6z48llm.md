---
title: "How I reduced the size of my Docker Image by 95%"
datePublished: Fri May 10 2024 05:49:04 GMT+0000 (Coordinated Universal Time)
cuid: clw09bpuw00180al8c6z48llm
slug: how-i-reduced-the-size-of-my-docker-image-by-95

---


Reduce the size of the Docker image using a Multi-Stage build

Writing a Dockerfile seems easy until and unless you end up writing Docker images having a size of 0.5GB. Yes, that’s true. I was recently working on a React JS Project, where I was building a front-end application. There was nothing new about the React JS Project. I was using the same package.json, the same set of dependencies that a typical frontend app would be using. Now, I decided to move the application to Kubernetes. So I pushed the docker image to DockerHub and tried to deploy a Pod.

I was using a local cluster and the pod took 5mins7sec to start. I was awestruck. And then I deployed it to the AKS Cluster ( Azure Kubernetes Cluster ). Surprisingly it took 3mins40sec. That was huge. I tried stressing the pod to trigger the Kubernetes HPA. The new pod takes the same 3 minutes to come up and eventually, the application gets overwhelmed with too many requests. Upon Investigation I figured out that the size of the image is the bottleneck, Of course, you don't want to have a docker image of such a huge size ( 0.5GB ). And that is when I realized that I would have to do something about the docker image size. Hence I utilized the concept of Docker multi-stage build.

## **What is the entire story all about? (TLDR)**

1. Reducing the size of Docker Images using Multi-Stage build.
    
2. Understand the Concept of Multistage build.
    

### **Docker Build:**

```dockerfile
FROM node:alpine
WORKDIR /app
COPY package.json ./
COPY package-lock.json ./
COPY ./ ./
RUN npm i
CMD ["npm", "run", "start"]
```

Here is my Initial Docker Image for a typical React JS Application. If you see line1, I was using the Alpine version of the node. After building the Dockerfile, here is the size of it.

![Non-multi Stage build](https://miro.medium.com/v2/resize:fit:736/1*lVLK9Qcbjc26H4GkJ-yPYg.png align="left")

Well, this is the typical way of building Images and it seems easy to write such docker files. But here are the disadvantages of using such an approach from the Kubernetes perspective.

a) The size of the image directly affects the Pod startup time.

b) The smaller the size of the image the faster the pod starts.

### **Docker Multi-Stage Build:**

Multistage builds feature in Dockerfiles enables you to create smaller container images with better caching and a smaller security footprint. With multi-stage builds, you use multiple `FROM` statements in your Dockerfile. Each `FROM` instruction can use a different base, and each of them begins a new stage of the build. You can selectively copy artefacts from one stage to another, leaving behind everything you don’t want in the final image.

```dockerfile
# Choose the Image which has Node installed already
FROM node:alpine as build

WORKDIR /code

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm ci --production
# COPY all the files from Current Directory into the Container
COPY . .

# Install the Project Dependencies like Express Framework
RUN npm run build

FROM nginx:1.22-alpine as prod

COPY --from=build /code/build /usr/share/nginx/html

# Tell that this image is going to Open a Port 
EXPOSE 80

# Default Command to launch the Application
CMD ["nginx", "-g", "daemon off;"]
```

Seems different? Alright, let us understand the file.

The first line is called as a stage. The stages are not named, and you refer to them by their integer number, starting with 0 for the first `FROM` instruction. However, you can name your stages, by adding an `AS <NAME>` to the `FROM` instruction.

And then the rest of the steps remain the same. <mark>One step that is the game changer here is the COPY — from ( Line 18 ).</mark> With multi-stage builds, you use multiple `FROM` statements in your Dockerfile. Each `FROM` instruction can use a different base, and each of them begins a new stage of the build. You can selectively copy artifacts from one stage to another, leaving behind everything you don’t want in the final image.

Let us build the image now.

![Size of the Image after multi-stage build](https://miro.medium.com/v2/resize:fit:736/1*2DCWPY6JKrGesWEqHpIJtA.png align="left")

* **Size of the Image after multi-stage build from the above image.**
    

***Wow, Yes!! That is true. The image size was reduced by 95%. The Image size is now 27.2 MB.***

![](https://miro.medium.com/v2/resize:fit:673/0*6jVGEauhNs8CkMHd.gif align="left")

My local cluster took 25 seconds to pull the image and get started. And my AKS Cluster took 10 seconds to pull the image and get started.

Isn’t this awesome :) !!

Well, that is how you utilize multi-stage built-in docker to reduce the size of your docker images. Please feel free to share your experience while working on these policies in the comment section.

***Until next time…..***

###