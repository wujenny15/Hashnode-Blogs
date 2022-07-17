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

### Types of storage accounts

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