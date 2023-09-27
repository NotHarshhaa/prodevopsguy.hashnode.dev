---
title: "Terraform Lifecycle Rules 101:"
datePublished: Wed Sep 27 2023 08:35:32 GMT+0000 (Coordinated Universal Time)
cuid: cln1hra1800020aid36i4ap0w
slug: terraform-lifecycle-rules-101
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1695802579399/aa30e4cd-46ce-4fb9-9ce0-dadfd2bc7273.png
tags: automation, devops, terraform, terraform-cloud, configuration-management

---

## **What is Terraform?**

Terraform is a free and open-source infrastructure as code (IAC) that can help automate the deployment, configuration, and management of remote servers. Terraform can manage both existing service providers and custom in-house solutions.

Read more about Terraform [**here**](https://developer.hashicorp.com/terraform/docs)**.**

## **Terraform Resource Behaviour:**

Once an object is created, it is saved in the Terraform state. Terraform can then update the object if its settings are changed in the configuration or destroy it if the `resource` is removed from the configuration.

Depending on the settings defined in the configuration, Terraform will take one of the following actions when applying the configuration:

* **Create** — Creates the object with the defined settings.
    
* **Destroy** — Destroys the object when the configuration no longer exists.
    
* **Update-in-place** — Updates the object accordingly when the settings in the `resource` block are changed.
    
* **Destroy and recreate** — Destroys the object before re-creating it, if certain settings change within the `resource` configuration block means this must happen on the given platform.
    

**Terraform behavior** Usually when we do any modifications on **terraform resources** where it’s already available; For example, consider resources like the EC2 instance that we created on the cloud already running. If we make some modifications for the **smaller changes**, they will **replace** the **arguments**.

* Create VPC in `us-east-1`
    

![](https://miro.medium.com/v2/resize:fit:421/0*BQ-sZEZ6fBmPKvUB.png align="center")

* When we do `terraform plan` will show a plan to create a new VPC.
    

![](https://miro.medium.com/v2/0*u_TfmLSfdYMMC_rE.png align="center")

* Run `terraform apply` to create a new VPC.
    
* Now, If I add the tag as `environment = dev` , this will just change the current VPC, As shown below.
    

![](https://miro.medium.com/v2/resize:fit:630/0*6dIJARSj5NvzJG3X.png align="center")

* When we make any big changes to the existing resource like changing the availability zone or instance type of EC2 instance, it will **destroy** the old resource and **replace** the new one, As shown below.
    

![](https://miro.medium.com/v2/resize:fit:447/0*iZtMAyRGbWeYZkL5.png align="center")

* This is the terraform default behaviour. For simple changes, it will just replace the arguments, For bigger changes, it destroys old resources and recreates them. This is not advisable to destroy after creation. After the destruction, we may face an issue with a new resource.
    

To avoid this, we have three lifecycle rules.

* **Create before destroy.**
    
* **Prevent destroy**
    
* **Ignore changes**
    

### **Create before destroy:**

* When Terraform determines it needs to destroy an object and recreate it, the normal behaviour will create the new object after the existing one is destroyed. Using this attribute will create the new object first and then destroy the old one. This can help reduce downtime. Some objects have restrictions that the use of this setting may cause issues with, preventing objects from existing concurrently. Hence, it is important to understand any resource constraints before using this option.
    

![](https://miro.medium.com/v2/resize:fit:682/1*VOtGHPkQCOC8yqRDIWSPrg.png align="center")

### **Prevent destroy:**

* This lifecycle option prevents Terraform from accidentally removing critical resources. This is useful to avoid downtime when a change would result in the destruction and recreation of `resource`. This block should be used only when necessary as it will make certain configuration changes impossible.
    

![](https://miro.medium.com/v2/resize:fit:469/1*0G-c05p_wy8FZL2gUm8xfQ.png align="center")

Terraform will error when it attempts to destroy a resource when this is set to true.

![](https://miro.medium.com/v2/resize:fit:736/1*5vUd3KQ4ql5ozc1uYt2DQw.png align="center")

### **Ignore changes:**

* This lifecycle option can be useful when attributes of a resource are updated outside of Terraform, for example, when an Azure Policy automatically applies tags. When Terraform detects the changes the Azure Policy has applied, it will ignore them and not attempt to modify the tag. Attributes of the resource that need to be ignored can be specified. **In the example below, the department tag will be ignored:**
    

![](https://miro.medium.com/v2/resize:fit:427/1*0zvIAJCXVoX3CizCZBDTCQ.png align="center")

* If all attributes are to be ignored, then `all` keywords can be used. This means that Terraform will never update the object but will be able to create or destroy it.
    

![](https://miro.medium.com/v2/resize:fit:398/1*Wi5cS7NWl-tHCYNtF3HJyQ.png align="center")

If you find this article helpful then you can [**buy me a coffee**](https://www.buymeacoffee.com/harshhaareddy)

Follow for more stories like this 😊.