## AZ305 Study Summary Week1

## Azure Reserved IPs
#### What is Azure Reserved IPs?
- Azure reserves 5 IP addresses within each subnet. 
- x.x.x.0: Network Address
- x.x.x.1: Default GW
- x.x.x.2 , x.x.x.3: DNS Mapping. Reserved by Azure to map the Azure DNS IPs to the VNet space.
- x.x.x.255: Network broadcast address

#### Specify the difference with AWS reserved IPs

- x.x.x.1: Reserved by AWS for the VPC router

- x.x.x.3: Reserved by AWS for future use.

---
## Azure Service Bus

#### What is Azure Service Bus ?
Azure service bus is a messaging system in Azure. There are mainly two kinds of services in Azure service bus. One is Azure service queue, the other one is Azure service topic.

#### Compare Azure Service Queue & Azure Service Topic ?

Azure service queue provide first in and first out message (FIFO) delivery. The receiver will reveive the messages in the order in which they are received.The published will send the message to the queue and the message will be send to the consumer.

The Azure service topic will pulish the message based on the topic . The message will be available to all the subscribers based on the topic they have selected.  

---
## Azure Import/Export Services

#### What is Azure Import/Export Services?
Azure Import/Export services is a secure and reliable to ship the on-premises data to the Azure Blob Storage and Azure Files. So user will fill in the form and then physically ship the disk drive to the Azure Data Center. With this service, we can also export the data to disk drive and then ship it back to customers.

#### When we should use Azure Import/Export Services
* when download the data from Internet is a bit slow. (Bandwidth Restrictions)
* Move the Data to the cloud
* Content distribution
* Backup

#### Support storage types
Azure Import/Export service supports the following storage types

- Import supports Azure Blob storage and Azure File storage
- Export supports Azure Blob storage

Azure Import/Export service supports the following of storage accounts:

- standard general purpose v2 storage accounts 
- blob storage accounts
- general purpose v1 storage accounts(both classic or azure resources manager deployments)
---
## Azure SQL Database, Azure SQL Managed Instance and SQL Server on Azure Virtual Machines 

#### Compare Azure SQL Database, Azure SQL Managed Instance and SQL Server on Azure Virtual Machines
* **Azure SQL Database**: PaaS, Supports active geo-replication, auto-scale, availability-zones, hyperscale architecture

  > Service Tiers: Azure SQL Database offers three service tiers
  
   - General Purpose/ Standard : Designed for common workloads, offers budget-oriented compute and storage options.
   - Business Critical/Premium: Designed for OLTP application with high transaction rates and low latency I/O requirements.
   - Hyperscale: Designed for most business workloads. Hyperscale provides flexibility and high performance with independently scalable compute and storage resources.

* **Azure SQL Managed Instance**: Paas
* **SQL Server on Azure Virtual Machines**: IaaS

--- 

## Shared Acess Signature
#### What is shared access signature ?
Shared access signature (SAS) is a service of Azure Storage. It grants restricted access rights ro Azure storage resources.
* Grant it to clients who should not be trusted with storage account key
* Delegate access to a shared access signature 
* Grant access for a specified period of time
* An account-level SAS can delegate access to multiple storage services(i.e., blob, file, queue, table)

---

## Azure AD Application Proxy 
#### What is Azure AD Application Proxy?
Application Proxy is a feature of Azure AD that enables users to access on-premises web applications from a remote client. Application Proxy includes both the Application Proxy service which runs in the cloud, and the Application Proxy connector which runs on an on-premises server.

#### Why do we need to have Azure AD Application Proxy?
Azure AD Application Proxy provides secure remote access to on-premises web application. 

---


