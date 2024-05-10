---
title: "Azure DevOps Series - Azure Test Plans"
datePublished: Fri May 10 2024 05:50:44 GMT+0000 (Coordinated Universal Time)
cuid: clw09dvnd000409mqfcmp08st
slug: azure-devops-series-azure-test-plans

---


Azure Test Plans is a test management module within Azure DevOps that lets users manage test plans, test suites, and test cases for everyone in the software development process.

![](https://miro.medium.com/v2/resize:fit:802/1*8H34E66Ybi8Cf9GtKc6UkA.png align="left")

Using test plans, you can Azure Test Plans also provides a browser extension for exploratory testing and gathering feedback from stakeholders.

Activate the azure test plan trial period enable **Organization + User side**

![](https://miro.medium.com/v2/resize:fit:802/1*fr7_SAROUsE-ZinS_c4pKA.png align="left")

User level change

![](https://miro.medium.com/v2/resize:fit:802/1*E89s8oD3PTQf3-zIKry19w.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*5GL3uCNadRf_YE4AOdM4ww.png align="left")

Changes made

![](https://miro.medium.com/v2/resize:fit:802/1*tfAYzEahh0Jvwdhh-XCVIQ.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*IpKhwj47ZyyUt3UEsQMGtA.png align="left")

# **Access level**

* You should have **Basic + test plan** access to execute, create, and publish test cases
    
* To execute the **test cases using Test Runner**, you should have at least basic access
    
* To **run exploratory testing with the Feedback extension**, you should have stakeholder access
    

![](https://miro.medium.com/v2/resize:fit:802/1*nIl0kva47aETSO8n_igCeA.png align="left")

Create a Plan

![](https://miro.medium.com/v2/resize:fit:802/1*zvX3vtF2lBDq3aKXyiAUiw.png align="left")

C

![](https://miro.medium.com/v2/resize:fit:802/1*MvLTr4mF6Ykzp5b1RfCKCQ.png align="left")

A test suite is a set of tests designed to **check the functionality and performance of the software**. It collects individual test cases based on their specific purpose or characteristics.

The Azure Test Plans contain and **configure test suites and individual test cases**. Test suites are the collection of test cases. So, when you create a test plan, you must create test suites within it. Three types of test suites…

* **Static-based**: You can use these test cases to group out other test suites or test cases.
    
* **Requirement based:** These test suites are the basic test suites. They pull all the test cases for a given requirement.
    
* **Query based:** these test suites pull a group of test cases from your project as per the requirement.
    

![](https://miro.medium.com/v2/resize:fit:802/1*fwNoSoPKnfJmBnJ8-rCVcQ.png align="left")

Create some dummy data for azure test plan

Azure Bioards → Create a new work item → Epic

![](https://miro.medium.com/v2/resize:fit:802/1*Zawr-gOTVGefjC55VIzG-w.png align="left")

Save the Epic

![](https://miro.medium.com/v2/resize:fit:802/1*FM2XFzMb2IKtAIR0E3GKBw.png align="left")

Go to the azure boards → Select Epic

![](https://miro.medium.com/v2/resize:fit:802/1*IXQVX9Jdjg4bSOdRCPsLjg.png align="left")

Change the name Testing instead of UI Testing

![](https://miro.medium.com/v2/resize:fit:802/1*MywNDUnkdngOgeQi-rbT9Q.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*O2_dWqvqybAsGa2jZvLhrQ.png align="left")

Goto the azure test suite and change the work item type “**Microsoft.EpicCategory**”

![](https://miro.medium.com/v2/resize:fit:802/1*b9ghFucLG1y4_EPo7g6kTg.png align="left")

Run a query → Create suites

![](https://miro.medium.com/v2/resize:fit:802/1*6doT_g0cua7hdmJNKNU6Yw.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*kUcUd3SpWIXXFmdrgzaB5Q.png align="left")

Add the test case

![](https://miro.medium.com/v2/resize:fit:802/1*d0w7C0Z9Lo0sWuxeK194BA.png align="left")

Another one test case created

![](https://miro.medium.com/v2/resize:fit:802/1*oFuBPr8W0dW95-6FwxbBWg.png align="left")

Assign the test case for someone (users)

![](https://miro.medium.com/v2/resize:fit:802/1*Gb9mrngcefD7OOrIdseZ-A.png align="left")

The **test hub** provides a central place for all test planning, execution, and analysis. Test hub **displays the results of test runs**. This includes all test runs, both manual and automated.

![](https://miro.medium.com/v2/resize:fit:802/1*2K8nPgFQS9rP2LjADRX6uQ.png align="left")

Goto the azure board check the work item. The test case reflected to the board.

![](https://miro.medium.com/v2/resize:fit:802/1*YhORa0UFrHHd262uo9Zcsg.png align="left")

First install the test & case feedback extension. I already add

![](https://miro.medium.com/v2/resize:fit:802/1*tXRRKnm1K17F6hUrkTh4_A.png align="left")

Connect to the dev azure portal

![](https://miro.medium.com/v2/resize:fit:802/1*R_mCznanOPyFBoyH10CtyA.png align="left")

Select the project

![](https://miro.medium.com/v2/resize:fit:802/1*qYsNuKsArZBjMowLsnwcDw.png align="left")

Execute the test case

![](https://miro.medium.com/v2/resize:fit:802/1*Dn58RdG5lXovkLUY9Lu5ng.png align="left")

Manually stop the test case

![](https://miro.medium.com/v2/resize:fit:802/1*h4gkyjj1Pn0GdbiJy5W7Gg.png align="left")

Capture the screenshot

![](https://miro.medium.com/v2/resize:fit:802/1*Xa_eW0ee5LtKgg2g5SpDlg.png align="left")

![](https://miro.medium.com/v2/resize:fit:802/1*xzAu5UjzlT55TAegyBSwZQ.png align="left")

Finally check the test case

![](https://miro.medium.com/v2/resize:fit:802/1*jIUEVQf6LCrgTEYZEtyUeQ.png align="left")

Again run the second test case

![](https://miro.medium.com/v2/resize:fit:802/1*ChRSmO9K85wDbEvj_jvToA.png align="left")

Go to the azure board check the work item

![](https://miro.medium.com/v2/resize:fit:802/1*mp0x9G3Mc8l554Tx414qMQ.png align="left")

Finally check the report

![](https://miro.medium.com/v2/resize:fit:802/1*sQIU_rdAGLv7HAKLrTAudg.png align="left")

Thank you 🙏 for taking the time to read our blog.