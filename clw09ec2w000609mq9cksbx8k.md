---
title: "Docker for the Absolute Beginner"
datePublished: Fri May 10 2024 05:51:06 GMT+0000 (Coordinated Universal Time)
cuid: clw09ec2w000609mq9cksbx8k
slug: docker-for-the-absolute-beginner
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715791920819/e8003f59-f9e0-4887-a394-c6a01cae572e.png
tags: docker, beginner, devops, containers, devops-articles

---

**Docker** is a tool that allows developers to package their applications and all their dependencies into a single container. This container can then be easily transported and run on any machine that has Docker installed, without worrying about differences in the environment. It's like a standardized way of packaging and running software.

**What is the container?**

[![Docker container](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)

container is like a little package that has everything a program needs to run, making it easy to move around and run on different computers without causing any trouble.

The cool part is that this mini-computer (container) is like a superhero with a cape. It can run on any computer, no matter how different they are, because it brings its own special environment with it. It's a neat and tidy way to keep software organized and make sure it works the same way no matter where it goes.

[![container](https://res.cloudinary.com/practicaldev/image/fetch/s--OcWggh5y--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1z5zcued8ya2onerpzwt.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--OcWggh5y--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1z5zcued8ya2onerpzwt.png)

**Why do we need Docker?**

1. **Consistency:** Docker makes sure that the software works the same way on your computer, your friend's computer, or any computer. It keeps things consistent.
    
2. **Portability:** You can package up your software and its friends into a Docker container, and it can travel anywhere. It's like putting your game and all its rules in a suitcase and playing it at a friend's house.
    
3. **Isolation:** Docker containers are like little bubbles. What happens inside the bubble stays inside the bubble. This means one program in a container won't mess with another program outside its container.
    
4. **Efficiency:** Docker helps save computer resources. Instead of having a whole computer just for one program, you can have many containers running on the same computer without them getting in each other's way.
    
5. **Speed:** Docker makes it quick and easy to start, stop, and share software. It's like turning on and off a game console – fast and simple.
    

**What is Docker Image?**

[![Docker Image ](https://res.cloudinary.com/practicaldev/image/fetch/s--Qc9f1gIv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/817t1rsad728snnighkj.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--Qc9f1gIv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/817t1rsad728snnighkj.png)

**Docker image** is a snapshot of a program and all the things it needs to run. It's a packed-up version that includes the code, tools, and settings, just like a snapshot of your cookie recipe with all the ingredients.

**The image is the recipe, and the container is what you get when you follow that recipe to actually make and run the program.**

**Some Basic Docker Commands.**

[![Basic Docker Commands](https://res.cloudinary.com/practicaldev/image/fetch/s--SDAX4S1D--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xq1pwt8896lvster3ppl.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--SDAX4S1D--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xq1pwt8896lvster3ppl.png)

1. `docker run nginx`
    
    * This command tells Docker to run a container using the "nginx" image. It's like telling Docker to start a new instance of a pre-made program (nginx, which is a web server).
        
2. `docker ps`
    
    * Shows you a list of running containers. It's like checking to see which programs are currently running.
        
3. `docker ps -a`
    
    * Shows you a list of all containers, including the ones that have stopped. It's like checking a history of all the programs you've run.
        
4. `docker stop silly_sammet`
    
    * Stops a running container named "silly\_sammet." It's like turning off a program that's currently running.
        
5. `docker rm silly_sammet`
    
    * Removes a stopped container named "silly\_sammet." It's like throwing away the instructions for a program you don't need anymore.
        
6. `docker images`
    
    * Lists all the Docker images you have. It's like looking at a menu of all the different programs you can run.
        
7. `docker rmi nginx`
    
    * Removes the "nginx" image. It's like erasing the recipe for a program you don't want to use anymore.
        
8. `docker pull nginx`
    
    * Downloads the "nginx" image from the internet. It's like getting a new recipe from a cookbook.
        
9. `docker run ubuntu sleep 5`
    
    * Runs a container using the "ubuntu" image and makes it sleep for 5 seconds. It's like starting a program that just waits for a little bit and then stops.
        
10. `docker exec distracted_mcclintock cat /etc/hosts`
    
    * Executes a command inside a running container named "distracted\_mcclintock." It's like peeking inside the recipe book to see a specific page.
        
11. `docker run -d kodekloud/simple-webapp`
    
    * Runs a container in detached mode from the "kodekloud/simple-webapp" image. It's like starting a program and letting it run in the background.
        
12. `docker attach a043d`
    
    * Attaches your terminal to a running container with the ID "a043d." It's like jumping into a running program to see what's happening.
        

**Some Docker concepts:**

1. **Run with a Tag:**
    
    * Tags are like versions of a program. It's specifying which version you want to run.
        
    * Example Code: `docker run nginx:latest`
        
    * This runs the latest version of the Nginx program.
        
2. **Run with STDIN:**
    
    * STDIN is like typing on your keyboard. Some programs want input from you.
        
    * Example Code: `docker run -i -t ubuntu`
        
    * This runs an interactive terminal inside a Ubuntu container, allowing you to type commands.
        
3. **Run with Port Mapping:**
    
    * Ports are like doors. Programs use them to communicate with the outside world.
        
    * Example Code: `docker run -p 8080:80 nginx`
        
    * This runs Nginx, and it opens the door on your computer's port 8080, connecting it to the container's port 80.
        
4. **Run with Volume Mapping:**
    
    * Volumes are like shared folders. They let you store things outside the container.
        
    * Example Code: `docker run -v /your/local/folder:/container/folder nginx`
        
    * This runs Nginx and connects a folder on your computer to a folder inside the container.
        
5. **Inspect Container:**
    
    * Inspecting is like taking a closer look at a running program.
        
    * Example Code: `docker inspect container_name`
        
    * This gives you detailed information about a running or stopped container.
        
6. **Container Logs:**
    
    * Logs are like a diary. They record what a program has been doing.
        
    * Example Code: `docker logs container_name`
        
    * This shows you the logs or activities of a specific container.
        

## Environment variables

environment variables are like handy notes that programs use to find important information, kind of like secret messages for the program to understand and work better!

1. **Environment Variables in a Python Script (**[**app.py**](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)**):**
    
    * Imagine you have a program ([app.py](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)) written in Python. You might want to customize it without changing the code. You can use environment variables.
        
    * Example Code ([app.py](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)):
        
    
    ```python
     import os
    
     app_color = os.getenv("APP_COLOR", "default_color")
     print(f"The app color is {app_color}")
    ```
    

* Running the script normally: `python`[`app.py`](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)
    
* Running with a specific color: `export APP_COLOR=blue; python`[`app.py`](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)
    

1. **Using ENV Variables in Docker:**
    
    * Docker containers can also use environment variables. It's like giving instructions to the program inside the container.
        
    * Example Code:
        
        * `docker run -e APP_COLOR=green simple-webapp-color`
            
        * This runs a Docker container (`simple-webapp-color`) and sets the environment variable `APP_COLOR` to "green".
            
2. **Inspecting Environment Variables:**
    
    * Sometimes, you want to check what environment variables a running container is using.
        
    * Example Code: `docker inspect blissful_hopper`
        
    * This command provides detailed information about the container named "blissful\_hopper," including its environment variables.
        

In simple terms, environment variables are like little notes that a program (or a Docker container) can read to know how to behave. You can set these notes before running the program, and the program will use them to customize itself. The `export` command in the second example is like writing a note before running a program, telling it how to behave. The `docker inspect` command is like peeking inside a container to see what notes it has.

## Docker Images

**Dockerfile:**

A Dockerfile is like a set of instructions for Docker to create an image. It's like a recipe for baking a cake.

```dockerfile
# Use the Ubuntu base image
FROM Ubuntu

# Update apt repository
RUN apt-get update

# Install dependencies using apt
RUN apt-get install -y python

# Install Python dependencies using pip
RUN pip install flask
RUN pip install flask-mysql

# Copy source code to /opt folder
COPY . /opt/source-code

# Set the working directory
WORKDIR /opt/source-code

# Specify entry point to run the web server
ENTRYPOINT ["flask", "run"]
```

**Steps to Create Your Own Image:**

1. Create a file named `Dockerfile` with the above content.
    
2. Save it in the same directory as your source code.
    

**Building the Docker Image:**  
Run the following command in the terminal:

```bash
docker build -t your-image-name .
```

This command tells Docker to build an image using the Dockerfile in the current directory (`.`), and tag it with a name of your choice (`-t your-image-name`).

**Layered Architecture:**

[![Layered Architecture](https://res.cloudinary.com/practicaldev/image/fetch/s--LBiWiTJK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9i91e79dg61wnbbfp62m.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--LBiWiTJK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9i91e79dg61wnbbfp62m.png)

* Think of the Docker image as a layered cake. Each instruction in the Dockerfile adds a layer to the image.
    
* Layers are reusable. If you change something in your code, Docker only rebuilds the layer affected, making it efficient.
    

**Docker Build Output:**

* When you build an image, Docker shows each step in the process. If there's a failure, it'll give you an error message.
    

**What Can You Containerize?**

* Almost anything! Applications, services, databases, websites, basically any software can be containerized.
    
* It's like putting your software in a box so it can run anywhere without causing trouble.
    

## **What is Docker CMD vs ENTRYPOINT**

`CMD` in Docker:

* Think of CMD as the default thing your program does when you start the container.
    
* It's like saying, "Hey, when you run this container, do this by default."
    
* Example: `CMD ["flask", "run"]` means when the container starts, it automatically runs the Flask web server.
    

**CMD Example:**

```dockerfile
FROM alpine
CMD ["sleep", "5"]
```

In this example, when you run a container using this image, it automatically sleeps for 5 seconds.

`ENTRYPOINT` in Docker:

* Think of ENTRYPOINT as the main thing your container does. It's like the boss command.
    
* It sets a default application to run when the container starts, but you can still override it if you want.
    
* Example: `ENTRYPOINT ["flask", "run"]` means the container is primarily meant to run the Flask web server, but you can still add more commands if needed.
    

**ENTRYPOINT Example:**

```dockerfile
FROM alpine
ENTRYPOINT ["sleep"]
CMD ["5"]
```

Here, the primary purpose is to sleep, and you can still override the sleep duration if you want.

In both cases, the container will just sleep for a few seconds when started. The key difference is in how you provide parameters and whether or not they can be easily overridden.

CMD is like saying, "Here's a default thing to do," and ENTRYPOINT is like saying, "This is the main thing to do, but you can tweak it a bit if you want." They both help define what your container does when it starts.

## **Networking in Docker:**

Docker networking helps containers (programs) talk to each other, making sure they can work together smoothly.

**Default Networks:**

* Docker creates default networks for containers to communicate.
    
* Example Code: `docker run ubuntu --network=host`
    
    * This runs a Ubuntu container using the host network, meaning it shares the network namespace with the host.
        

**User-Defined Networks:**

* You can create your own networks for better organization and control.
    
* Example Code:
    

```bash
  docker network create --driver=bridge --subnet=182.18.0.0/16 custom-isolated-network
```

* This creates a user-defined bridge network named `custom-isolated-network` with a specific subnet.
    

**Listing Networks:**

* You can see all the networks you have.
    
* Example Code: `docker network ls`
    

**Inspecting a Network:**

* You can inspect the details of a specific network.
    
* Example Code: `docker network inspect blissful_hopper`
    
    * This shows detailed information about the network named "blissful\_hopper."
        

**Embedded DNS:**

* Docker has a built-in DNS system for containers to find each other by name.
    
* Example Code: `mysql.connect(mysql)`
    
    * This could be a line in your code where a service named "MySQL" connects to another service named "MySQL" using Docker's DNS.
        

## Docker Storage:

[![Docker Storage](https://res.cloudinary.com/practicaldev/image/fetch/s--ESsHx2Oz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7i54a6m0o1tb0812xbjk.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--ESsHx2Oz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7i54a6m0o1tb0812xbjk.jpg)

Docker storage is like deciding where to keep your data when using containers. You can keep them inside the container, share them between containers using volumes, or store them outside the container for safekeeping.

**File System in Docker:**

* Docker uses a layered architecture to build images. Each instruction in the Dockerfile adds a new layer to the filesystem.
    

```dockerfile
# Dockerfile
FROM Ubuntu
RUN apt-get update && apt-get install -y python
RUN pip install flask flask-mysql
COPY . /opt/source-code
WORKDIR /opt/source-code
ENTRYPOINT ["flask", "run"]
```

* The layers in the Dockerfile:
    
    * Layer 1: Base Ubuntu layer
        
    * Layer 2: Changes in apt packages
        
    * Layer 3: Changes in pip packages
        
    * Layer 4: Source code
        
    * Layer 5: Update Entry point with "flask" command
        
    * Layer 6: Container Layer
        

**Image Layers:**

* When you build a Docker image, it consists of read-only layers. Each layer represents a change or addition to the image.
    
    * Layer 1: Base Ubuntu layer
        
    * Layer 2: Changes in apt packages
        
    * Layer 3: Changes in pip packages
        
    * Layer 4: Source code
        
    * Layer 5: Update Entry point with "flask" command
        

```bash
# Build the Docker image
docker build -t mmumshad/my-custom-app .
```

**Container Layer:**

* When you run a Docker container, a read-write layer is added on top of the read-only image layers. This layer is specific to the running container.
    
    * Layer 6. Container Layer
        

```bash
# Run the Docker container
docker run mmumshad/my-custom-app
```

**Volumes:**

* Volumes are a way to persist data outside the container. They are like external storage.
    

```bash
# Create a Docker volume
docker volume create data_volume

# Use the volume in a container
docker run -v data_volume:/var/mysql mysql
```

* You can also mount specific directories from the host to the container using `-v`:
    

```bash
# Mount a host directory to a container directory
docker run -v /path/on/host:/var/mysql/mysql -d mysql
```

* The docker run --mount command is used to mount a specific directory or file from the host machine into a running Docker container.
    

```bash
docker run --mount type=bind,source=/mysql,target=/var/mysql mysql
```

**Storage Drivers:**

* Docker uses storage drivers to manage how data is stored and accessed. Some common storage drivers include AUFS, ZFS, BTRFS, Device Mapper, Overlay, and Overlay2.
    

[Manage data in Docker](https://docs.docker.com/storage/)  
[About storage drivers](https://docs.docker.com/storage/storagedriver/)  
[Volumes](https://docs.docker.com/storage/volumes/)

## **Docker Compose**

[![Docker Compose](https://res.cloudinary.com/practicaldev/image/fetch/s--QQ4Lw1Nm--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yjyro6o2844s2or1b83c.jpeg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--QQ4Lw1Nm--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yjyro6o2844s2or1b83c.jpeg)

***Docker Compose is a handy tool that helps you easily run and connect different software services as if they were all part of the same event***.

**Docker Compose Basics:**

1. **Running Individual Containers:**
    
    * Normally, you might run separate Docker containers like this:
        
    
    ```bash
     docker run mmumshad/simple-webapp
     docker run mongodb
     docker run redis:alpine
     docker run ansible
    ```
    
2. **Docker Compose File (**`docker-compose.yml`):
    
    * Docker Compose allows you to define all these services in a simple file:
        
    
    ```yaml
     # docker-compose.yml
     version: '3'
    
     services:
       web:
         image: 'mmumshad/simple-webapp'
       database:
         image: 'mongodb'
       messaging:
         image: 'redis:alpine'
       orchestration:
         image: 'ansible'
    ```
    

* This file describes the services you want to run (`web`, `database`, `messaging`, `orchestration`), their respective images, and any additional configurations.
    

1. **Running with Docker Compose:**
    
    * To start all these services together:
        
    
    ```bash
     docker-compose up
    ```
    

* Docker Compose takes care of starting all the containers defined in your `docker-compose.yml` file.
    

1. **Building with Docker Compose:**
    
    * You can also build images using Docker Compose:
        
    
    ```bash
     docker-compose build
    ```
    

* This command builds the images specified in the `docker-compose.yml` file.
    

**Running Linked Containers:**

* If you were to run individual containers with linking:
    
    ```bash
     docker run -d --name redis redis
     docker run --name voting-app -p 5000:80 --link redis:redis voting-app
     docker run --name result-app -p 5001:80 --link db:db result-app
     docker run -d --name worker --link db:db --link redis:redis worker
    ```
    
* In Docker Compose:
    
    ```yaml
     # docker-compose.yml
     version: '3'
    
     services:
       vote:
         image: 'voting-app'
         ports:
           - '5000:80'
         links:
           - 'redis:redis'
       result:
         image: 'result-app'
         ports:
           - '5001:80'
         links:
           - 'db:db'
       worker:
         image: 'worker'
         links:
           - 'db:db'
           - 'redis:redis'
       db:
         image: 'db'
       redis:
         image: 'redis'
    ```
    

Docker Compose lets you describe your entire application stack in a single file, making it easy to manage, run, and connect different services. It's like writing down all the tasks for your event in one plan, and then Docker Compose handles the setup for you.

[Docker Compose overview](https://docs.docker.com/compose/)  
[Docker compose Doc](https://docs.docker.com/engine/reference/commandline/compose/)

## **Docker Registry**

[![Docker Registry](https://res.cloudinary.com/practicaldev/image/fetch/s--Z4w9W9N6--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bzflp82qyg36y8fcf8k8.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--Z4w9W9N6--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bzflp82qyg36y8fcf8k8.png)

a Docker Registry is a place where people store and share their Docker images, making it easy for others to use and run their software. It's like a big online library for programs that can be easily downloaded and used on different computers.

**Docker Registry Basics:**

1. **Public Registry:**
    
    * Docker images can be stored and shared on public registries like Docker Hub.
        
    * Example:
        
    
    ```bash
     docker pull nginx
    ```
    
2. **Private Registry:**
    
    * Sometimes, you might want to keep your images in your own private registry.
        
    * Example:
        
        * Log in to a private registry:
            

```bash
bash
       docker login private-registry.io
```

```bash
 - Run a container from an image in the private registry:
```

```bash
   ```bash
   docker run private-registry.io/apps/internal-app
```

````yaml

1. **Deploying Your Own Private Registry:**
    
    * You can deploy your own private registry for your team or company.
        
    * Example:
        
        * Run a private registry on your machine:
            

```bash
docker run -d -p 5000:5000 --name registry registry:2
{% endraw %}
     - Tag your image for the private registry:
{% raw %}
````

bash  
docker image tag my-image [localhost:5000/my-image](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)

```basic
- Push the image to your private registry:
```

bash  
docker push [localhost:5000/my-image  
\`\`\`](https://res.cloudinary.com/practicaldev/image/fetch/s--VBR-50Zw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/imsgbstga86vnxjwgebr.png)

```bash
 - Pull the image from your private registry:
```

```bash
  bash
       docker pull localhost:5000/my-image
```

1. **Pulling from a Remote Private Registry:**
    
    * You can also pull images from a remote private registry using its IP address or domain.
        
    * Example:
        
    
    ```bash
     docker pull 192.168.56.100:5000/my-image
    ```
    

a Docker Registry is like a storage space where people keep and share their Docker images. You can use public registries for widely-used images or set up your own private registry for your specific needs. It's like a special library for sharing and storing software blueprints (images).

## **Docker Engine**

[![Docker Engine](https://res.cloudinary.com/practicaldev/image/fetch/s--O5JwzlxK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hc6r4dvo9kg9xqgwsrbb.jpg align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--O5JwzlxK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hc6r4dvo9kg9xqgwsrbb.jpg)

Imagine you have a magic box (Docker Engine) that can run and manage all kinds of programs (containers) for you. Docker Engine is like the brain of this magic box.

1. **Docker Daemon:**
    
    * The Daemon is like the caretaker of the magic box. It's always there, ready to take instructions and make sure everything runs smoothly.
        
2. **REST API:**
    
    * Think of REST API as a set of rules that allow you to talk to the magic box. It's like a language that you and the Daemon use to communicate. You tell the Daemon what to do, and it understands because you're speaking the same language.
        
3. **Docker CLI (Command Line Interface):**
    
    * The Docker CLI is like a magical wand you use to command the Daemon. You type in commands, and the Daemon follows your instructions. It's like saying "Abracadabra" to make things happen.
        

**Connecting to a Remote Docker Engine:**  
connecting to a remote Docker engine allows you to control containers on another machine, and setting constraints ensures that containers use only specified resources.

1. **Docker Host IP:**
    
    * You can connect to a Docker engine on a different machine using its IP address and port.
        
    * Example:
        
    
    ```bash
     docker -H=remote-docker-engine:2375 run nginx
    ```
    

* This tells your local Docker CLI to communicate with a remote Docker engine.
    

1. **Running Container with Constraints:**
    
    * Docker allows you to set resource constraints for containers, like CPU and memory limits.
        
    * Example:
        
    
    ```bash
     docker run --cpus=0.5 ubuntu
     docker run --memory=100m ubuntu
    ```
    

* These commands limit the container to use only half a CPU core and 100 megabytes of memory.
    

Sure, let's simplify the concept of PID namespace:

**Namespace PID:**

PID namespace allows you to create a separate area for processes (like programs or tasks) in a container, so they have their own set of "ticket numbers" (Process IDs) that don't clash with processes outside the container.

**Example Code:**

1. **Running a Container with Host PID Namespace:**
    
    * This means the container shares the same "ticket numbers" as the host.
        

```bash
   docker run --pid=host ubuntu
```

1. **Running a Container with Isolated PID Namespace:**
    
    * This means the container has its own set of "ticket numbers" separate from the host.
        

```bash
   docker run --pid=container ubuntu
```

In the first example, the container interacts with processes as if it's in the same space as the host. In the second example, the container has its own isolated space for processes. It's like having a private area in a big event where your group has its own set of ticket numbers, allowing you to do things independently of the rest of the event.

**Containerization Concepts:**

1. **Process ID Namespace:**
    
    * Containers have their own isolated process ID (PID) space, so processes inside a container are separate from those outside.
        
    * Example:
        
    
    ```bash
     docker run --pid=host ubuntu
    ```
    

```bash
 - This command runs a container with the host's PID namespace, so it shares the same processes.
```

1. **Network Namespace:**
    
    * Containers also have their own isolated network namespace, meaning they can have their own network configurations.
        
    * Example:
        
    
    ```bash
     docker run --net=host nginx
    ```
    

```bash
 - This command runs a container with the host's network namespace.
```

1. **Unix Time Sharing Namespace:**
    
    * This namespace allows containers to have their own view of time, separate from the host and other containers.
        
    * Example:
        
    
    ```bash
     docker run --uts=host ubuntu
    ```
    

```bash
 - This command runs a container with the host's Unix time sharing namespace.
```

1. **Inter Process Mount Namespace:**
    
    * Mount namespace isolates the file system, allowing containers to have their own file system view.
        
    * Example:
        
    
    ```bash
     docker run --mount=type=bind,source=/host/folder,target=/container/folder ubuntu
    ```
    

```bash
 - This command mounts a folder from the host into the container.
```

Certainly! Let's simplify the concept of cgroups:

**Cgroups:**

cgroups (short for control groups) help manage and distribute system resources, such as CPU and memory, among different processes or containers. They ensure that no single process or container uses up all the available resources, keeping everything balanced.

**Example Code:**

1. **Setting CPU Limit with Cgroups:**
    
    * This is like saying each guest at the party can only eat a certain amount of food.
        

```bash
   docker run --cpus=0.5 ubuntu
```

* This limits the container to use only half of a CPU core.
    

1. **Setting Memory Limit with Cgroups:**
    
    * This is like saying each guest can only take up a certain amount of space on the dance floor.
        

```bash
   docker run --memory=100m ubuntu
```

* This limits the container to use only 100 megabytes of memory.
    

[Docker Engine overview](https://docs.docker.com/engine/)  
[Develop with Docker Engine API](https://docs.docker.com/engine/api/)  
[Runtime metrics](https://docs.docker.com/config/containers/runmetrics/#control-groups)

## **The concept of Linux Containers and Windows Containers:**

**Linux Containers (Default):**

Linux containers are a way to package and run software along with everything it needs, and they are most comfortable on computers that run Linux.

**Windows Containers:**

Windows containers are a way to package and run software, just like Linux containers, but they are designed to work on computers that run Windows.

**Windows Containers Basics:**

1. **Container Types:**
    
    * Windows Containers come in two main types: Windows Server Core and Nano Server.
        
        * **Windows Server Core:** Think of it as a more fully-featured container, suitable for a variety of applications.
            
        * **Nano Server:** Think of it as a lightweight container, designed for specific, minimalistic use cases.
            
2. **Base Images:**
    
    * Base images are like the blank canvas you start with when creating a container.
        
        * Example:
            
    
    ```bash
       docker pull mcr.microsoft.com/windows/servercore:ltsc2019
    ```
    

```bash
   - This command pulls the Windows Server Core base image.

 - Example:
```

```bash
   ```bash
   docker pull mcr.microsoft.com/windows/nanoserver:ltsc2019
```

````yaml

```bash
   - This command pulls the Nano Server base image.
````

1. **Supported Environments:**
    
    * Windows Containers can run on specific versions of the Windows operating system.
        
        * Example:
            
        * You can run Windows containers on Windows Server 2016.
            

```bash
 - Example:
   - You can run Windows containers on Windows 10 Professional and Enterprise, with Hyper-V Isolated Containers for additional isolation.
```

## **Container orchestration**

[![Container orchestration](https://res.cloudinary.com/practicaldev/image/fetch/s--jwowFYB4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3lyleybojw3xmr2dgfep.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--jwowFYB4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3lyleybojw3xmr2dgfep.png)

container orchestration is a way to manage and coordinate multiple containers, making sure they work together seamlessly to run applications, just like a super-smart manager making sure all the robots work together to build a perfect tower.

**Why orchestration?**

1. **Many Tasks, One Manager:**
    
    * Imagine you have many robots (containers) doing different jobs. Orchestration is like having one super-smart manager (orchestrator) who tells each robot what to do and ensures everything happens smoothly.
        
2. **Consistency:**
    
    * Orchestration makes sure all tasks are done the same way every time. It's like having a set of instructions for your robots to follow, ensuring consistency in their actions.
        
3. **Efficiency:**
    
    * Orchestration helps optimize tasks, making sure resources (like time and materials) are used efficiently. It's like a manager making sure all robots work together without wasting energy.
        
4. **Scaling:**
    
    * When you need more work done, orchestration can easily create additional robots (containers). It's like magically summoning more robots to help when there's a lot to accomplish.
        
5. **Reliability:**
    
    * Orchestration ensures that tasks are completed reliably, even if a robot (container) fails. It's like having a backup plan to make sure the job gets done no matter what.
        
6. **Coordination:**
    
    * Orchestration coordinates tasks, making sure robots work together seamlessly. It's like the manager making sure each robot knows its role and collaborates to achieve the overall goal.
        

**Container Orchestration Code:**

```bash
# Create a Docker service with 100 replicas (instances) of a Node.js application
docker service create --replicas 100 --name my-nodejs-app nodejs
```

In this example:

* `docker service create`: This command tells Docker to create a service, which is a group of running containers.
    
* `--replicas 100`: This flag specifies that you want 100 instances (replicas) of your service.
    
* `--name my-nodejs-app`: This flag gives a name to your service, in this case, "my-nodejs-app."
    
* `nodejs`: This is the image or recipe for your Node.js application. It's like the blueprint for baking cupcakes.
    

So, this simple code is like telling your magical chef's assistant (Docker Swarm) to create 100 replicas of your Node.js application, ensuring that you have a lot of containers running and ready to serve.

## **Docker Swarm**

[![Docker Swarm ](https://res.cloudinary.com/practicaldev/image/fetch/s--dj5bq6ig--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z5noonjo2ikyrp90kc38.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--dj5bq6ig--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z5noonjo2ikyrp90kc38.png)

Docker Swarm is a tool that helps coordinate and manage a group of computers (nodes) to work together as a team of robots, allowing them to deploy and run multiple containers in a coordinated manner. It's like having a chief robot manager making sure all the individual robots build something big and amazing together.

**Setting up Docker Swarm:**

1. **Swarm Manager:**
    
    * Imagine you have a chief robot (Swarm Manager) that leads the team. The chief robot decides what needs to be done and directs the other robots (nodes) on how to work together.
        

```bash
   # Initiate Docker Swarm on the Swarm Manager
   docker swarm init
```

1. **Node Worker:**
    
    * Now, you have worker robots (Node Workers) ready to join the team. The Swarm Manager shares a special code (token) to invite them to work together.
        

```bash
   # Join a Node Worker to the Docker Swarm
   docker swarm join --token <token> <Swarm Manager IP>
```

**Docker Swarm Service:**

Now that you have a coordinated team, you want to create a service, like building towers with your robot team:

```bash
# Create a Docker service (a group of containers) with 3 replicas (instances)
docker service create --replicas 3 --network frontend --name my-web-server my-web-image
```

* `--replicas 3`: This flag tells Docker to create three instances (replicas) of your service.
    
* `--network frontend`: This flag specifies that your service belongs to a network called "frontend."
    
* `--name my-web-server`: This gives a name to your service, in this case, "my-web-server."
    
* `my-web-image`: This is the image or blueprint for your web server. It's like the recipe for building the towers.
    

You set up your robot team with a chief (Swarm Manager) and worker robots (Node Workers). Then, you instruct them to build a service (group of containers) that runs your web server application. The chief robot ensures that three replicas of your web server are created and connected to the "frontend" network. It's like having a chief robot manager overseeing the construction of multiple towers (containers) with the help of the worker robots.

GIF

![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--Kp5Kl81C--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ytitz2wt4jsufejox9yx.gif align="left")

**Okay, that’s it for this article.**

**Thank you for reading this article, and see you soon in the next one! ❤️**