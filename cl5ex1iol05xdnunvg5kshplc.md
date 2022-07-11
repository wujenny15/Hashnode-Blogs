## AZ305 Study Summary Week3

## Azure Front Door

### What is Azure Front Door?

Azure front door is a routing service. It is a global service which is available to route requests based on performance and based on the least latency. It has routing methods. So if there are two region, us and europe , you can check the current latency by visting the latency test website, and you will find that Azure Front Door actually route traffic to region that has least latency set up.

### Compare Azure Front Door with Azure Traffic Manger and Azure APP gateway

It has similar routing methods like Azure traffic manger and it has URL path based routing, in addtion to these two, it also has a SSL offloading.

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

Azure Data Factory is Azure’s cloud ETL service for scale-out serverless data integration and data transformation. Azure Data Factory is a cloud based data integration service that orchestrates data movement & transformation between diverse data sources and cloud compute resources
