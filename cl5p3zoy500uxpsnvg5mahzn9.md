## AZ305 Study Summary Week4

## Shared Access Signature (A service of Azure Storage)

A shared access signature (SAS) is a URI that grants restricted access rights to Azure Storage resources. You can provide a shared access signature to clients who should not be trusted with your storage account key but whom you wish to delegate access to certain storage account resources. By distributing a shared access signature URI to these clients, you grant them access to a resource for a specified period of time.
An account-level SAS can delegate access to multiple storage services (i.e. blob, file, queue, table). Note that stored access policies are currently not supported for an account-level SAS.

---

## Azure Conditional Access Policy

### License Requirements
At least Azure AD premium P1 license.

### What is Azure Conditional Access Policy
It can control users access based on conditional access policy to bring signals together, to make decisions, and enfore organization policies.

---

## Border Gateway Protocol
BGP breaks the entire internet into over twenty thousand autonomous systems, often simply called “AS”. AS is a group of one or more router networks under the control of a single entity like a big ISP, a branch of the federal government, a big university system. “AS” has direct or indirect control of all the routers , all the networks, all the subnets within their own “AS”. Every AS has 32 bit autonomous system, the vast majority of assets that are actually out there and working for a living. Since autonomous systems have total control on their own network routes, they can route between routers any way they want, and it’s usually done via OPF. But as far as the internet is concerned, we don’t care when these autonomous systems interconnect though, they must use BGP. BGP only do one thing well, that is route data between autonomous systems. A router sending a chunk of data out to the internet only needs to know where its own BGP router is.

---

## Azure Event Hubs
### What is Azure Event Hubs?
Azure Event hub is a big data streaming platform. The service can receive and process millions of events per second. You can stream log data, telemetry data or any sorts of events to Azure Event Hubs.

### Event Hubs Architecture

- The different components.
- Event producers: This is an entity that sends data to an event hub. The events can be published using the protocols , https, amqp, Apache Kafka
- Partitions : The data is split across partitions. This allows for better throughput of your data onto Azure Event Hubs.
- Consumer groups: This is a view (state,position, or offset) of an entire evenet hub.
- Throughput: This controls the throughput capacity of event hubs
- Event Receivers: This is an entity that reads event data

---

## Types of storage accounts

[storage account type](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview#types-of-storage-accounts)

Stroage account:
- Premium file shares: Azure file shares can support a maximum of 5TB, whereas premium file share(currently in preview) can support a file share of up to 100TiB/
- Page blobs: Page blobs are made up of 512-byte pages up to 8TB in total size and are dwsigned for frequent random read/write operations/

---

## Azure SQL Databases Security

### Transparent Data Encryption
The data stored in the data center is encrypted and stored at rest by default. When you access the data, the data will be decrypted. Even the data is secure in the data center, some company require another level of security. By default, transparent data encrption is enabled by default for SQL databases.

### Always Encrypted Feature
The always encrypted feature can be used to encrypt data at rest and in motion. You can encrypt multiple columns located in different tables. You can encrypt multiple columns located in the same table. You can just sncrypt one specific column.

2 types of encryption:
- Deterministic encryption - Here the same encrypted value if generated for any given plain text value. This is less secure. But if allows for point lookups, equality joins, grouping and indexing on encrypted columns.
- Randomized encryption - This is the most secure encryption method. But it prevents searching, grouping, indexing and joining on encrypted columns.

We can enable the always encrypted feature using SQL server management studio. There are 2 keys that get created when the always encrypted featre is enabled for a database. 

- Column master key - This is an encryption key that needs to be stored in an external data store. Here you can store the key in a Windows certificate store or in the Azure Key vault service.
- Colum Encryption Key - This is generated from the column master key and is used to encrypt the actual column.

The user who is implementing the Always Encrypted feature needs to have the following permission for keys - create, get, list, sign, verify, wrapKey, unwrapKey.

### Dynamic Data Masking
Here is the data in the database table can be limited in its exposure to non-priviledged users. You can create a rule that can mask the data. Based on the rule you can decide on the amont of data to expose to the user,

There are differnet masking rules

- Credit Card masking rule - This is used o mask the column tha contain credit card details. Here only the last four digits of the field are exposed. 
- Email - Here first letter of the email address is exposed. And the domain name of the email address is replaced with xxx.com
- Custom text 
- Random number

--- 
## Azure Service Fabric
Service Fabric allows you to build microservice based applications. Here you can deploy the different services of your microservice based applications. Service Fabric has the capability to automatically detect and restart failed services. Service Fabric can also automatically discover services and route messages between services. Applications can be deployed as a process or in a container. You can create a service fabric environment anywhere. It can be on your local computer, on a ser of virtual machines or on Azure.

## Azure Front Door

### What is Azure Front Door?

Azure front door is a routing service. It is a global service which is available to route requests based on performance and based on the least latency. It has routing methods. So if there are two region, us and europe , you can check the current latency by visting the latency test website, and you will find that Azure Front Door actually route traffic to region that has least latency set up.

### Compare Azure Front Door with Azure Traffic Manger and Azure APP gateway

It has similar routing methods like Azure traffic manger and it has URL path based routing, in addtion to these two, it also has a SSL offloading. Azure Front Door supports rate limiting.  The Azure Web Application Firewall (WAF) rate limit rule for Azure Front Door controls the number of requests allowed from clients during a one-minute duration. Azure Front Door is the only service can support rate limiting when compared with Azure Traffic manger profile, Azure Load Balancer,  Azure Application Gateway

---
## Azure Traffic Manager

Azure traffic manager is a DNS routing based service. The traffic is routed based on DNS. It has a Azure traffic manager profile. So user will hist the Azure Traffic Manager profile. You might have three app service which is hosted in east us, central us and east us2. So it is a gloabl service and it can route traffic to different endpoints. It has multiple routing methods.

- priority. You have two endpoints, You set diff priority. It will route traffic to endpoints with higher priority and if first endpoint breakdown, it will route to second endpoints.
- weightage. Your can let 30% of traffic go to endpoint a, 30% go to endpoint bm, 40 % go to endpoint 4.

### Compare with Azure Load Balancer

Azure load balancer is a network routing tool. This route traffic is based on the IP address, TCP protocol. The azure Load balancer can only route traffic to service which are in the same region.

---

## Data Redundancy

Data redundancy means multiple copies of your data are stored. This helps to protect against planned and unplanned events including transient hardware failures, network or power outages.

- Locally-redundant storage: Three copies of your data are made in the same data center, so it helps to protect against sercer rack of drive failures.
- Zone-redundant storage: It help to protect against data center level failures. Data is replicated synchronously across three Azure availability zones. Each availability zone is a separate physical location with independent power, cooling and networking.
- Geo-redundant: Data is replicated to another region. Data is copied three times in the primary region using LRS and Data is also copied three times in the seconday region using LRS.
- Read-access geo-redundant storage: The data is replicated similarily to the geo-redundant storage. But unlike the geo-redundant storage, the read-access geo-redundant storage can read data from any region at the same time while geo-redundant storage can read data from only one region
---

## Azure Logic App

### What is Azure Logic Apps

Azure logic app is a cloud service that helps you schedule, automate and orchestrate tasks, business processes and workflows.

### How it works

- You first design a workflow in Azure Logic Apps
- Each workflow starts with a trigger
- The trigger is fired via a specific event
- When the trigger is fired, the logic app engine creates a logic app instance that runs the workflow

### Connectors for Azure logic apps

These connectors provide easy access to event,data, actions that are sent from external applications, services, systems or platforms.

You have built-in connectors that can connect to Azure services such as Azure Functions, Azure API apps etc.

You have managed connectors that can connect to platforms such as office 365, Microsoft Dynamics.

---

## Azure AD Domain Services

### What is Azure AD Domain Services?

Azure AD domain services is a managed version of a traditional on-prem Active Directory. It offers domain join, group policy, LDAP, kerberos, and NTLM authentication. It does not require deployment or management of domain controllers. Azure AD domain services consists of a DNS namespaces and a matching directory for that namespace. It rides on top of or even integrated with existing Azure AD tenant. 

Azure AD domain service is compatible with cloud only Azure AD tenants. Compatible with Azure AD tenants that are synced with an on-prem AD. Users synced into Azure AD will show up in Azure AD domain services.

cloud-only best practice:

create resource in Azure Active Directory and let them sync over to the managed domain service.

hybrid best practice:

create users in the on-prem AD so then synchronize over to Azure Actice Directory with Azure AD connect.

After syncing to Azure AD, they will sync to Azure AD domain services.

### Benefits of Azure ADDS

Azure AD domain services is tightly integrated with Azure Active directroy. Azure ADDS support Kerberos & NTLM autehntication.

Allows you to deploy applications that rely on Windows integrated authentication. Simplified lift and shift of application to Azure/

### How does Azure AD DS work?

When Azure ADDS is deployed, a managed domain is created on the virtual network that we specify. And then Azure spins ip two windows server domian controllers that run on VMs. You don’t need to manage or configure these domain controllers in any way. You can’t manage or access the domain controllers. Azure performs all management of the domain controllers.

The managed domain spun up is configured for one-way synchronization from Azure AD

### Compare with Azure AD

Look at Azure AD tenant as the vehicle for users to sign in with credentials while Azure active directory domain services is the vehicle for provising advanced management because Azure AD domain services replicated the identity information form your Azure AD tenant.

---

## Azure Functions hosting options

There are mainly three Azure Function hosting plans for Azure functions.

- consumption plan: pay as you go, scales automatically, default option
- premium plan: need more CPU or memory, support virtual network connectivity, provide a custom linux image to run the functions
- dedicated plan: for long-running scenarios, have a underutilized VMs available to use.

---

## Azure Site Recovery

### What is Azure Site Recovery?

Azure Site Recovery is a business continuity solution. Suppose you have a Azure virtual machine in the primary region and it is business critical. So you need to make sure it can run in the secondary region when it fails in the primary region. You need to make sure that all the data in the first region can be replicated to the secondary region.

### What can Azure Site Recovery do?

- Provide the ability to recover in the event of a regional outage
- Support a recovery time objective (RTO) of 15 minutes.
- Support a recovery point objective (RPO) of 25 hours. One hour for application consistency and five minutes for crash consistency.

---

## Azure Migrate

If you have physical servers that you want to migrate Azure virtual machines. Azure migrate service can work with Hyper-V/VMware. Azure migrate service is actually we can do an azure assessment and migration of your workloads. So you will know the size of the VM and migrate to Azure virtual machines. And based on the Azure Migrate, you can perform a replication of the workloads, and then perform a test and final migration. Metadata discovered by the Azure Migrate appliance helps you to figure out whether servers are ready for migration to Azure, right-size servers, plan costs and analyze application dependencies.

---
 
## Managed Identity

Managed identity helps Azure resources to authenticate to services that support Azure AD authentication. So instead of using azure application service principal id and service principal secret. So we assign the identity to the vm which is hosting the application, and then the app can azure storage account. You don’t need to provide any form of the secret.

- system-assigned managed identity: System-assigned managed identity cannot be shared. It can only be associated with a single Azure resource.
- user-assigned managed identity: User-assigned managed identity can be shared. The same user-assigned managed identity can be associated with more than one Azure resource.

---

## App Service Environment

###What is App Service Environment?

The idea of App Service environment is deploy the entire app service inside of the virtual network. All app service environments have a public IP tha is used for inbound management traffic. With App service environment v2, you can deploy an internal load balanced app service environment or an external ASE. With the external ASE, you can use the public IP address as the endpoint to resolve http/https, FTP/FTPS, web deployment, remote debugging.

---
## Azure Host Groups

What is a host group?

A host group is a resource that represents a collection of dedicated hosts. You create a host group in a region and an availability zone and add hosts to it. 

![Screen Shot 2022-07-05 at 7.01.49 pm.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657432916884/LRPxy3011.png align="left")

--- 
## Azure API management

### The benefits of Azure API management

- helps to manage API’s easier
- You can change the behaviour of API’s via policies
- You have in-built cache’s
- You can implement better security for your API’s

---

## Azure App Service

- Azure Web App can write Application log - [https://docs.microsoft.com/es-es/azure/app-service/troubleshoot-diagnostic-logs](https://docs.microsoft.com/es-es/azure/app-service/troubleshoot-diagnostic-logs)
- Azure web App can read/write files to local file system - [https://github.com/projectkudu/kudu/wiki/Understanding-the-Azure-App-Service-file-system](https://github.com/projectkudu/kudu/wiki/Understanding-the-Azure-App-Service-file-system)
- Azure web app is less expansive that a VM scale set (VM scale is thinked for a long number of VM)

---

## Azure ExpressRoute

### What is Azure ExpressRoute?

Allows you to connect your on-premises networks to Microsoft cloud over a private connection. Here the connection is established with the help of a connectivity provider. The ExpressRoute connection does not go over the public internet. The connection is more reliable, and faster and you get less latency, we will get two connections for each ExpressRoute circuit for redundancy.

---

## Azure Data Factory

Azure Data Factory is Azure’s cloud ETL service for scale-out serverless data integration and data transformation. Azure Data Factory is a cloud-based data integration service that orchestrates data movement & transformation between diverse data sources and cloud compute resources

Azure Data Factory is the platform that solves such data scenarios. It is the cloud-based ETL and data integration service that allows you to create data-driven workflows for orchestrating data movement and transforming data at scale. Using Azure Data Factory, you can create and schedule data-driven workflows (called pipelines) that can ingest data from disparate data stores. You can build complex ETL processes that transform data visually with data flows or by using compute services such as Azure HDInsight Hadoop, Azure Databricks, and Azure SQL Database.

## Azure Time Series Data (TSI)

### What is Azure Time Series Data?

It is a fully managed PaaS solution built for IoT

- ingest, process, store and query IoT scale data
- Connect to a variety of data solutions using Azure Time Series Data’s flexible data platform
- Use rich analytics APIs and UX for ad-hoc exploration and operational intelligence

### Why we want to use Azure Time Series Data.

- IoT data lacks structural consistency
- IoT data needs contextualization
- IoT data is characterized by infinite retention
- IoT data is used with other data from

---

## Azure SQL Auditing

### What is Azure SQL Auditing?

Azure SQL Auditing tracks database events and writes them to an audit log in Azure storage account, log analytics workspace or event hub.

When we enable the Azure SQL Auditing, we can save the audit log to the storage account which is located in the same location of the Azure SQL. The storage account which can store the audit log does not support premium storage currently.

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

  ##### Resource Limits
  Basic: 2GB
  Standard: 1TB
  Premium: 4 TB

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

## What are five pillars of Azure well-architected framework pillars?

- Cost optimization
- Operational excellence
- Performance efficiency
- Security
- Reliability

> what's the difference between operational excellence and performance efficiency?
Operation excellence focus on the speed of deployment, fasten develpment cycle with the help of DevOps. Monitoring tools to detect it earlier.
