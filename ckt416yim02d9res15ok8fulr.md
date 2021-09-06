## Azure Fault Domain & Update Domain


"Ask Me About Azure" is a series of articles about Azure Cloud Services. I am a DevOps and cloud engineer who enjoys helping people to learn cloud computing. I will try my best to explain cloud concepts in chat-style writing and help you understand Azure in a fun and easy way. 

🐤 : Represents little yellow duck who is learning hard..


## Azure Fault Domain & Update Domain

🐤 I am preparing AZ104 exam and I am not sure how to workout the below question.

Qustion: You plan to move a distributed on-premises app named App1 to an Azure subscription. After the planned move, App1 will be hosted on several Azure virtual machines. You need to ensure that App1 always run on at least eight virtual machines during planned Azure maintenance. What should you create ?

- A. one virtual machine scale set that has 10 virtual machines instances
- B. one Availability Set that has three fault domains and one update domain
- C. one Availability Set that has 10 update domains and one fault domain 
- D. one virtual machine scale set that has 12 virtual machines instances

>  Let me help ! First of all, what do you know about Fault domain and Update domain.

🐤 Yeap, I watched <a href="https://www.youtube.com/watch?v=ilXx0cmmGz0">John Savill's video </a> and understood that:

- Azure is fundamentally racks of servers
- A fault domain is a rack of servers (hardware component), and it might fail because of power supply and etc.,
- When we deploy 2 VMs in a availabity set, Azure will place them in 2 fault domains (2 different racks) so that when rack1 go down, it won't affect the VM in rack2. So the service can keep running.
- Update domain is a logical group of hardwares that can undergone maintenance. When we create VMs in an availability set, Azure will distributes VMs across update domains and only one update domain will be reboot at a time.

![rackofserver.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630576057435/DcR-PgXna.png)

Yes, when we create our availability set in Azure, it has its preconfigured fault domains and update domains.

>Azure have 2 fault domains and 5 update domains by default. 

Azure might have other default fault domains and update domains in the future. (eg., 3 fault domains and 6 update domains). We should know how many fault domains and update domains are there first. 

![aset.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1630575306484/G5oqD1WCMy.png)

## Further clarification
Take this question as an example, we will assume it has 2 fault domains and 5 update domains since it doesn't mention how many fault domains and update domains. If we have 10 VMs, it will be placed in 2 fault domains and each rack will have 5 VMs. 

And 10 VMs will be distribute to 5 update domains logically, each update domain will have two VMs. So during the maintainance, only 1 update domain will be shut down. Which means we will have the remaining 8 VMs available. So the correct answer will be A.

![fd.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1630653024139/uQ2hFPTnq.jpeg)
Fault Domains
<hr>

![ud.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1630652185942/kjiAJqrC1.gif)
Update Domains
<hr>

## Practice On Your Own

Question1: You have an app named App1 that runs on two Azure virtual machines named VM1 and VM2. You plan to implement an Azure Availability Set for App1. The solution must ensure that App1 is available during planned maintenance of the hardware hosting VM1 and VM2. What should you include in the Availability Set?
- A. one update domain
- B. two fault domains
- C. one fault domain
- D. two update domains

Question2:<a href="https://www.examtopics.com/discussions/microsoft/view/29599-exam-az-104-topic-3-question-22-discussion/">Question from ExamTopics</a>

## Feedback

Let me know whether you understand update domains and fault domains. If you still don't understand, please let me know. I will try my best to explain it. I also need some feedback so that I can improve my writing and clarifications skills as well.

  



                                              
