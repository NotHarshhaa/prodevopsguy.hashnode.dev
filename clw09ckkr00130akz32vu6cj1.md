---
title: "2023 DevOps is terrible."
datePublished: Fri May 10 2024 05:49:43 GMT+0000 (Coordinated Universal Time)
cuid: clw09ckkr00130akz32vu6cj1
slug: 2023-devops-is-terrible

---


# **What is DevOps?**

If you are reading this post you already know it but for those in the back who don’t:

> *DevOps is a culture, a movement, a philosophy if you will; that aims to <mark>foster</mark> collaboration during the* ***Software Development Life Cycle****.*

DevOps is not a role or a set of tools or (just) a methodology.  
It is indeed achieved by adopting tools, approaching to software the (real) agile way, creating processes and yes, hiring the right people too.

I’ve been around the DevOps/Cloud area of the IT industry for a few years now

In time, I experienced the DevOps adoption processes multiple times, in different kind of companies from day-1 all set to moving monoliths to the Cloud.

*Good old manual SysAdmin with long and complex bash scripted deploys?*  
Been there, done that.  
*Rising peaks of setting up GitOps in the cloud and spinning pods in a few clicks?*  
Tell me about it.

From just giving more responsibility of the Operations to Software Engineers to making Ops people aware of the software they were deploying and operating.

![](https://miro.medium.com/v2/resize:fit:526/0*oRwPuA9cgqWWENu2.jpg align="left")

Yep, unfortunately enough Docker doesn’t solve all of your issues.

Like all the good things, in time, DevOps shifted to be something it is not.  
A job title and a buzzword more than anything.  
A role in which people are supposed to deal with a confessionary set of Cloud-related tasks ranging from the complex management of Kubernetes Clusters to the repellent manual IAM onboarding.  
Ticket storming at them all day, left and right, leaving little time for meaningful tasks.

# ***The shift***

Big techs aside, there are a few companies out there, able to implement and manage DevOps at scale and even some of those successful companies end up throwing away money, time and a number of engineers in the process.

Let’s dive into what I think could be some causes of this DevOps drift.

**1\. DevOps/Cloud teams are overbooked**

On the bright side, if your company has a DevOps/Cloud team your are already one step ahead of your competitors: yay!

Wait a minute, this team handles: databases, networking, security policies, roles, cloud environments, accesses and security too.  
Most probably through a messy IaC repository, writing poor Terraform code with little if any naming convention, no templating, all carefully handcrafted and repeated throughout your code base.

![](https://miro.medium.com/v2/resize:fit:736/0*-GmCgKeebCe9AMjW.png align="left")

Or maybe it is just an illusion

You will soon discover how fast both your Software Engineering team and DevOps people can get frustrated, witnessing the effects of sedimented DevOps.

**2\. Silos are (never really) broken, infrastructure is!**

Keeping everybody on track, aiming towards the same objective is not a walk in the park, even when you managed to break the infamous “silos”.

![](https://miro.medium.com/v2/resize:fit:505/1*jRqLifH66gVRGR4kEsIquw.gif align="left")

The (in)famous silo being broken

Engineers get excited when building new stuff, not when manually maintaining old legacy items over and over, even if necessary.

We come to a never-ending dilemma: **rigidity** is needed to handle infrastructure and avoid continuous maintenance, but **flexibility** is also needed in order to adapt components to ever-changing real-world requirements.

*A Mexican standoff.*

We end up doing things quick and dirty in order to not get too frustrated and mostly to catch up with some impossible product deadline, which somehow never takes into account Ops.

*I’m looking at you, product people, be aware of the Ops time!*

**3\. Create, configure, repeat**

Sometimes DevOps means copy-pasting the same code for every new instance/cluster/environment.  
CTRL-C-CTRL-V-as-a-service and nobody really cares about it as long as that fix is done.

![](https://miro.medium.com/v2/resize:fit:427/1*t_xVbJagT3wPzX9e8UHEvA.gif align="left")

Everybody (but that single repo nobody remembers about) gets a fix

That fix works until everything falls apart and it needs to be propagated in multiple repos without ever knowing if all the projects have been really fixed at that point.

*Sounds funny, right?*

**4\. Software Engineering boundaries**

Software Engineers should not manage policies, roles, keys or be too aware of cloud regions, availability zones or networking in general.

*These are kinda boring tasks for a SWE and definitely feels like old-fashioned filling paperwork.*

![](https://miro.medium.com/v2/resize:fit:505/1*ztezWwq4op_JTuag23mPDg.gif align="left")

In the best case scenario code deployment should be as smooth as pushing on a git repo and everything else, infrastructure included, handled by some auto-magic black box.

# **The solution**

So what? Should we go back to Stone Age without any DevOps?  
Of course not!

The IT industry has lately given its answer on the topic:

[**Platform Engineering**](https://platformengineering.org/blog/what-is-platform-engineering).

![](https://miro.medium.com/v2/resize:fit:524/1*EdnOhdQ9vIoWMc67tElgDw.gif align="left")

Classic Platform Engineering in the first implementaton phase

Flexible building blocks, customizable by experts and usable by any engineer, in a self-service fashion.

> ***You build it, you run it****, you deploy it, you test it, you monitor it, but for real.*

Considering DevOps as a double lane road to success, Platform Engineering can be pictured like a highway with guardrails, many more lanes, traffic management, police and toll booths.

# **Explaining Platform Engineering**

*What is this Platform Engineering about?*  
In three words: [**Internal Development Platform**](https://internaldeveloperplatform.org/).

You basically build a product for the best (or worst?) customer ever: your own engineering team.

*Need to create a new API?*  
Just spin it up on the IDP, in a few second you can start writing your business logic and everything else is handled, auth and boilerplate code included!

*No config for your need?*  
You can try to take the nearest existing one to adapt it with just a few lines of YAML.

*What if a need changes or a new one arrives?*  
No biggie, let you Platform team build something from scratch and from that moment onwards everyone else can use it whenever they need.

*This IDP seems cool but for real, what is it?  
***A composable platform with a catalogue/marketplace** from which your teams can basically “shop” whatever they need to deliver value in way less time than without it.

* Core components: git integrations, authentication/authorization standardized mechanisms, secrets handling, SSL certificates generation…
    
* Blueprints for apps, CI/CD and even infrastructure code
    
* An acceptable level of security, handled by design
    

So what should I do with my DevOps teams? Ditch them?

![](https://miro.medium.com/v2/resize:fit:526/0*kJh3KIPi0cYROfew align="left")

Oh no.

Stop right there and listen!  
Verticality is needed, more than ever. Platform Engineering allows Software Engineers to go back (just) coding and encourages the experts to collaborate in building something truly amazing such as an IDP.  
DevOps are needed, Kubernetes ninjas are welcome and even a good old database administrator can be useful!

# **Key features of an IDP**

* **Frontend** — GUI should be developer friendly;
    
* **Extendibility** — Building blocks, blueprints, well-defined templates, modules, a catalogue;
    
* **Streamlined operations** — Ways to standardize: provisioning, configuration, CI/CD, observability, environment management and multitenancy;
    
* **Ease of experimentation** — All the good things at a click distance to serve the engineers and enable their creativity aka “support whatever tool they need in an agnostic way”;
    
* **Low lock-in mechanisms** — Avoid a platform based on closed-source tools or just a single cloud provider;
    
* **Security, Governance, Compliance** — RBAC, logging, monitoring, alerting, auditing, login and access management, secrets, api keys, licenses… Easily accessible without learning tons of domain specific languages;
    

*What if I wanna build my own IDP from scratch?*  
Yes, you surely can, but, and this is a strong opinion I have, you shouldn’t start from zero, **re-inventing the wheel all the time**.  
That’s part of what an IDP should solve!

A few examples of IDPs?

* [Backstage](https://backstage.io/)
    
* [Humanistic](https://humanitec.com/)
    
* [Mia Platform](https://mia-platform.eu/)
    
* [Port](https://www.getport.io/)
    
* [Portainer](https://www.portainer.io/)
    
* [Upbound](https://www.upbound.io/)
    

I’m not endorsed by any of the companies behind these products, even if it would be nice of them.  
*Where is my money, huh?*

Jokes aside, I may have left behind other amazing pieces of software, feel free to drop some names in the comments.

Summarizing: Platform Engineering?  
**A natural evolution of DevOps.**

2023 DevOps?  
Not terrible.  
You’ve just been click baited again!

![](https://miro.medium.com/v2/resize:fit:736/0*kR-9cHjlmIWHRjkA.jpg align="left")

Gotcha.

If you find this article helpful then you can [**buy me a coffee**](https://www.buymeacoffee.com/harshhaareddy)**.**

Follow for more stories like this 😊/ [**GitHub**](https://github.com/NotHarshhaa)**.**