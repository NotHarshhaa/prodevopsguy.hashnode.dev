---
title: "Azure DevOps Series - Azure Repos"
datePublished: Fri May 10 2024 05:50:40 GMT+0000 (Coordinated Universal Time)
cuid: clw09ds7m00010am9ca7yfdzp
slug: azure-devops-series-azure-repos
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715321256577/acb96492-3448-41e8-90a5-78c75a47661e.png
tags: azure, devops, azure-devops, azure-certified, devops-articles

---


Azure Repos is a set of **version control tools** that you can use to manage your code. Whether you work with a team or independently, Azure Repos provides **Git repositories** (or) **Team Foundation Version Control** (TFVC) for source control of your code.

![](https://miro.medium.com/v2/resize:fit:658/1*CuG2NZDwcKU1WyFhIQR13Q.png align="left")

It’s integrated with Azure DevOps, a suite of tools that **cover the entire software development lifecycle**, from planning and project management to CI/CD and monitoring.

![](https://miro.medium.com/v2/resize:fit:783/1*Z32AFqvu8OvBuvKdvdEgtQ.png align="left")

**Azure Repos supports two types of Version Control:**

* Git
    
* TFVC ( Team Foundation Version Control)
    

![](https://miro.medium.com/v2/resize:fit:802/1*xYngTw573JRew4rxGM0Z2A.png align="left")

**Git**

**Git** is a version control system that lets you manage and keep track of your source code history. **GitHub** is a cloud-based hosting service that lets you manage Git repositories.

More Git 👉 [**Click the link**](https://ibrahims.medium.com/git-full-zero-to-hero-ece15d47b66a)

**TFVC**

**Team Foundation Version Control (TFVC)** is a **centralized** version control system. Typically, team members have only one version of each file on their dev machines. Historical data is maintained **only on the server**. Branches are path-based and created on the server.

Configure the VSCode Git client using

```yaml
git config --global credential.helper wincred
git config --global user.name "Ibrahim S"
git config --global user.email Ibrahimsi909@hotmail.com
```

![](https://miro.medium.com/v2/resize:fit:802/1*FLDYxr18Wh2cUHjJ634ncg.png align="left")

Goto the last project **PartsUnlimited**

Repos → Files → Clone → Clone in VS Code

![](https://miro.medium.com/v2/resize:fit:802/1*o43ydKvROVFUU_rSaRUrGA.png align="left")

Clone the repository on VS Code

![](https://miro.medium.com/v2/resize:fit:802/1*XpV54BNDggyqu22D2zDMjg.png align="left")

PartsUnlimited repository cloned successfully let make the changes to source code

![](https://miro.medium.com/v2/resize:fit:802/1*F_YR9wvmAUhc2SKQQfC9gQ.png align="left")

Save & Commit the code

![](https://miro.medium.com/v2/resize:fit:628/1*SeWQsL2lhPaiaGXI-8U0Ag.png align="left")

Finaly sync the code to remote repository

![](https://miro.medium.com/v2/resize:fit:646/1*HdrhKUG0UutXr0kpEd178w.png align="left")

Goto the azure devops the code is commit or not?

![](https://miro.medium.com/v2/resize:fit:802/1*GeU7E8zTt--bzTAzEe6Xrw.png align="left")

If you get the old code go to the previous commit code and you clone (or) download the old code

![](https://miro.medium.com/v2/resize:fit:802/1*RRrOYZTZlxalDToD3YCPCA.png align="left")

**Branch** is an independent line of development. It works as a **pointer** to your next commits. Whenever a new branch is created, Git creates a new pointer while keeping the original code base untouched.

> *Branch is a pointer to one specific commit, while a commit is a snapshot of your repository at a specific point in time*

**Five types of branches, each with different roles:**

* Main branch.
    
* Feature branch (i.e., Topic branch)
    
* Release branch.
    
* Hotfix branch.
    
* Develop branch (i.e., Integration branch)
    

![](https://miro.medium.com/v2/resize:fit:802/1*yeSiHKBYZ1zSGWgBFacBGQ.png align="left")

A **local branch** exists only on your local machine. All the changes you introduce and commit to your local repository are stored only on your local system. Create a branch using the below command.

```yaml
git branch <branchname>
git checkout -b <branchname>
git branch <branchname> <tag>
git branch <branchname> <commit id>
```

**Remote branches** are how developers collaborate on the same project simultaneously. A remote branch exists in a remote repository (most commonly referred to as origin by convention) and is hosted on a platform such as GitHub.

```yaml
git remote -v
git remote add origin git@github.com:github URL
git push origin master 
```

![](https://miro.medium.com/v2/resize:fit:802/1*G_Tt-Ab55dQqBqyf9psEAQ.png align="left")

**“Origin”** remote refers to the default remote repository that is created when a Git repository is cloned. This remote repository is typically the central repository that is used to share changes and collaborate with other developers.

Find out the branch.

![](https://miro.medium.com/v2/resize:fit:678/1*8i_uHZA5g-deKeJgOOAu-w.png align="left")

Create a new branch and switch out the new one.

![](https://miro.medium.com/v2/resize:fit:802/1*8oCaM-k8ejE0ip-HFKyuzA.png align="left")

Created a branch in azure repo

![](https://miro.medium.com/v2/resize:fit:802/1*RY5ss4o4Fc-1WSK_qR9w7w.png align="left")

**Git pull** copies changes from a remote repository directly into your working directory.

**Git fetch** command only copies changes into your local Git repo.

Locking a branch will make the branch read-only and ensures that no commits can be made to the branch.

Locking a branch prevents other users from changing the existing commit history.

**Tags** in git are valuable for marking significant points in your project’s history, documenting releases, and providing a clear reference for important milestones.

**Pull Requests** are specific requests to merge changes from one branch into another.

Thank you 🙏 for taking the time to read our blog.