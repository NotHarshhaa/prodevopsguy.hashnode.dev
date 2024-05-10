---
title: "Explaining Kubernetes To My Uber Driver"
datePublished: Fri May 10 2024 05:49:31 GMT+0000 (Coordinated Universal Time)
cuid: clw09cbe3000708jsdvpjhido
slug: explaining-kubernetes-to-my-uber-driver

---


![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700640667627/948fe81e-dbc7-44dc-9f6e-64c710a7b7a4.png align="center")

Imagine coming out of a 3-day conference, and not being able to describe the technology to your Uber driver. *Facepalm.* So, in an attempt to redeem myself, here’s my reimagined conversation with my Uber driver.

# Start of Conversation

**Me**: Imagine you’re a chef at a busy restaurant kitchen. You’ve got a team of chefs working for you, and each one is preparing a different part of the meal - one group for appetizers, one for main courses, and another for desserts. Coordinating these chefs to make sure the meal is served to the customer on time is your job. Do you have a picture in your head?

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--jI8Tke76--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bn0xlqpdw7vw2lcg4a2u.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--jI8Tke76--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bn0xlqpdw7vw2lcg4a2u.png)

**Driver**: Got it.

**Me**: In this scenario, the head chef is Kubernetes. Just like the head chef needs to manage all the different chefs in the kitchen, Kubernetes helps manage all the different pieces needed to run your software. The official definition of Kubernetes is a “container-orchestration tool”, but since the word “container” is pretty abstract here, you can substitute the word “container” for “chef”. So Kubernetes would be a "chef orchestration tool". That way, you can form a picture in your head of your kitchen every time you hear the word.

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--AFKdhaKH--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kzyqf05ebfv8tn9kkt4i.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--AFKdhaKH--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kzyqf05ebfv8tn9kkt4i.png)

**Driver**: Okay, that makes sense so far. But what are these containers? I can't keep imagining them as chefs forever.

**Me**: Yeah good point. So now that you have a picture in your head of your Kubernetes kitchen, let’s dive into how all the different kitchen roles map to Kubernetes concepts, going from smallest to largest.

> Container  
> The smallest part of this puzzle is the container, and it’s any piece of software. For example, it could be a Node.js web server that hosts a web application, or a MongoDB database container to store data *(this sentence is more for the engineers reading this blog, I wouldn’t say this to my Uber driver 😛)*. In the kitchen, imagine you’re serving soup and a salad for your appetizer. The soup would be your container. The salad would also be its container.

I know this definition seems a bit arbitrary right now, but it’ll make more sense once I explain it **in the context** of the upcoming components.

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--DnnOaweG--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oqpypznztr958j5n8ouh.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--DnnOaweG--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oqpypznztr958j5n8ouh.png)

> Pod  
> In the kitchen, a pod would be the plate/tray that holds your soup and salad. In Kubernetes, a pod is something that can hold 1 or more containers. The reason for this is that containers within a pod can communicate with each other.

**For the engineers**: as an example, imagine I have a container for a web server and a container for a database in my pod. They can communicate with each other over [localhost](https://dev.to/therubberduckiee/explaining-kubernetes-to-my-uber-driver-4f60#start-of-conversation).

As for an appropriate analogy with the kitchen, I can’t think of anything. Imagine some Sausage Party shenanigans where your anthropomorphized soup and salad start chatting to each other. But the soup and salad from the appetizer plate can’t talk to the steak and potatoes on the dinner plate because they are on different plates (aka, different pods don’t share the same network namespace and therefore can’t communicate with each other.)

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--0wATwiBR--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7fgcm20wc6fajrmju05x.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--0wATwiBR--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7fgcm20wc6fajrmju05x.png)

> Master Node  
> The head chef manages and oversees the entire kitchen. This is the concept of “container orchestration” or “chef orchestration” we talked about earlier. Some real-life examples of the orchestration work that this master node would do would be:
> 
> Scaling, aka adjusting up or down the number of running pods based on CPU utilization. In a busy kitchen, when there’s a surge in customer demand, chefs may need to scale up their operations by preparing more servings of a dish. By the way, one thing to note in this visualization - you’re probably imagining the kitchen hiring new chefs, but I want you to imagine it more like the current chefs are getting cloned. When scaling happens, pods are essentially being copied.
> 
> Automated deployment, aka defining your application’s dependencies & runtime instructions in a YAML file so it can deploy based on this configuration. In a kitchen, this YAML file is analogous to a written recipe that tells the chef how to make the dish to ensure consistency and efficiency and preparing it.
> 
> Load balancing, aka distributing network traffic across different pods. In the kitchen, load balancing involved assigning tasks to different chefs at a cooking station. Maybe Bob at the dessert station is overloaded with requests to scoop ice cream, so the master chef clones Bob and has Bob 2.0 take some of the ice cream orders off Bob 1.0’s hands.

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--MV449Uq4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/txdtcmoblfg5xk8w250x.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--MV449Uq4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/txdtcmoblfg5xk8w250x.png)

Also important to note: each worker node has something called a "kubelet". In the kitchen scenario, "kubelet" would be analogous to the chef at each table. The chef has a bunch of jobs, like making sure the trays of food are being assembled correctly, helping prep ingredients, and throwing away the scraps. Similarly, "kubelet" does things like ensuring containers within pods are running, helping with initializing pods (e.g. having necessary dependencies installed), helping with garbage collection, and more.

Some extra context for the engineers: Kubelet is an open-source, executable binary (aka file with machine code instructions that a CPU can directly execute), written in Go programming language.

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--vlspo5s9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/85hvn3eeq4xj6zxc36q6.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--vlspo5s9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/85hvn3eeq4xj6zxc36q6.png)

Let's stop here for a second. If you understand everything I've said up to this point, you understand the basics of Kubernetes architecture! If you don't want to rely on the kitchen imagery forever, I've replaced all the kitchen drawings with only Kubernetes terminology in the diagram below.

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--35f6HINT--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z7pg9fgbojmuvjt4q03q.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--35f6HINT--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z7pg9fgbojmuvjt4q03q.png)

**Driver**: Actually, all of this makes a lot of sense. So I get what Kubernetes is. But I still don't get why it's useful. Like what's the point of having it or learning about it?

**Me**: Yep, the last part of the puzzle is understanding **how** Kubernetes is used. How do humans interact with Kubernetes? How is Kubernetes relevant/useful in the world of technology? Let's lean back on our kitchen analogy for a second to explain some more concepts.

* The owner of the restaurant/franchise is analogous to the software developers who are building out an app or service. At Mcdonald's, the franchise owner (Let's say their name is Francis Cockadoodledoo) wants to get information on how much money each Mcdonald's location is making and has the ability to fire/hire employees as needed. To do this, Francis Cockadoodledoo may pick up their phone and call the master chef to get information and give orders. In Kubernetes, software engineers can't pick up a phone to interact with their Kubernetes cluster, but the “master node” has an API server that you can call, and this allows you to access all tasks. For example, engineers can get information on all the pods, nodes, and services, understand the health and metrics information, and have the ability to delete or create resources.
    
* The customers eating at the restaurant are analogous to the users of an app or service. Similar to how the McDonald's kitchen produces Big Macs for me to eat, the Spotify Kubernetes cluster provides me with the service of listening to a large selection of music from a web browser.
    

I've factored this new information into the drawing I've included below. What you'll see is very similar to the diagrams you'll see when you google "Kubernetes architecture".

[![Image description](https://res.cloudinary.com/practicaldev/image/fetch/s--qz96J8MN--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gjkqs8dct2kxnditkrlt.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--qz96J8MN--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gjkqs8dct2kxnditkrlt.png)

[![A diagram of Kubernetes architecture I pulled from the Internet](https://res.cloudinary.com/practicaldev/image/fetch/s--1AHq1eM---/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3ens8psibkxhn8f2oepa.png align="left")](https://res.cloudinary.com/practicaldev/image/fetch/s--1AHq1eM---/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3ens8psibkxhn8f2oepa.png)

And of course, I realize there are some abstractions I left out of my explanation because I felt like they were not important in forming a basic mental model of Kubernetes. Feel free to dig in more. As I dig in more myself, I may add to this blog with some links to resources I find useful.

# Conclusion

The reason why I picked this mode of storytelling (describing tech through the lens of a conversation with an Uber driver) is that I wanted to break down Kubernetes into something that was universally understandable and felt approachable.

If you find this article helpful then you can [**buy me a coffee**](https://www.buymeacoffee.com/harshhaareddy)**.**

Follow for more stories like this 😊/ [**GitHub**](https://github.com/NotHarshhaa)**.**