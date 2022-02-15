# Cloud Storage
I will mostly be discussing about cloud storage w.r.t GCP.

## Introduction
Cloud storage is a subcategory of cloud computing. Cloud storage refers to storage service model in which data is transmitted and stored on remote storage systems, where it is maintained, managed, backed up and made available to users over a network. Cloud computing systems offer users access to not only storage, but also processing power and computer applications installed on a remote network. The storage concept utilizes instant elasticity, scalability, multi-tenacy and storage infrastructure which provides accessible interface and virtualization. This means that cloud-based storage services have the capability of increasing or decreasing based on need and users generally pay according to the storage consumtion and the tier of storage being utilized.

At its most basic level, a cloud storage system needs just one data server connected to the Internet. A user can send files over the Internet to the data server, which then records the information. When the client wishes to retrieve the information, he or she accesses the data server through a Web-based interface. The server then either sends the files back to the client or allows the client to access and manipulate the files on the server itself.

Cloud storage systems generally rely on hundreds of data servers. Because computers occasionally require maintenance or repair, it's important to store the same information on multiple machines. This is called redundancy. Without redundancy, a cloud storage system couldn't ensure clients that they could access their information at any given time. Most systems store the same data on servers that use different power supplies. That way, clients can access their data even if one power supply fails.

Google Cloud Storage consists of four main components which are projects, buckets, objects, and access controls. The GCS lifecycle can be viewed as a project consisting of buckets, the bucket stores objects and the permissions to access and control the buckets and objects is configured using the access control management component. GCS stores unstructured data storing sequences of bytes on a location identified by a unique id. The sequence of bytes, termed as **objects**, can hold any information ranging from images to text files. GCS has no insights of data on its structure, it only receives objects and later returns them as requested by the user. The objects it receives are stored in buckets like how files are stored in a hierarchical structure in a normal operating system. Just because it stores data in the object format, it is highly scalable and facilitates fast access to data. It is also a great product for backup archives which are helpful in any disaster recovery and it also serves as an important component for regulation and compliance. 

## How storage works
Large data centers are maintained in multiple locations around the world. When customers purchase cloud storage from a provider, they turn over most aspects of the data storage to the vendor, including security, capacity, storage servers and computing resources, data availability and delivery over a network. Customer applications can access the stored cloud data through traditional storage protocols or application programming indicators (APIs), or they can also be moved to the cloud.

The most important features of cloud storage working are its reliability and security. The data being stored on the cloud storage buckets is encypted on the server side, before data is written to the disk, using AES-256. Furthermore, the encryted data is maintained/accessed using service like Ley Management Service (KMS), responsible for managing key encryption. Google Cloud KMS is part of the Google Cloud Platform (GCP) suite and enables customers to manage their encryption keys for data they store on GCP. Administrators can also use Google Cloud KMS to do bulk data encryption on plaintext before it is stored. The main industries Google targets with this service are those subject to regulations about how they store and secure sensitive data, like financial services and healthcare providers. 

Cloud KMS integrates with some of Google's other cloud services, such as Cloud Identity and Access Management, which handles encryption key authentication. Together, the services manage security permissions and policies that control key access and access to KeyRings. Cloud KMS also integrates with Cloud Audit Logging, which records administrative access and usage activity -- something that can be helpful when dealing with compliance standards and regulations. Automated and manual key rotation options enable users to apply a preset schedule or manually select when the encryption keys rotate. This is done using either the API or the command-line interface. Google Cloud KMS has the ability to support millions of encryption keys with an arbitrary number of key versions. It can be used as a distributed service or in a single geographical cloud data center.
[!KMS Control level](https://github.com/TheJacksonLaboratory/cloud-computing-for-genomics/blob/gh-pages/fig/GCP_KMS.png)

The other big concern, reliability, is just as important as security. An unstable cloud storage system is a liability. No one wants to save data to a failure-prone system, nor do they want to trust a company that isn't financially stable. While most cloud storage systems try to address this concern through redundancy techniques, there's still the possibility that an entire system could crash and leave clients with no way to access their saved data. Google claims to deliver 99.9% or better uptime through its highly available, geo-redundant data-replication system.

**Storage Class**
The classes are categorised by the data access frequency:
Standard: High availability, performance, and suitable for frequently accessed and short live data
Nearline: Highly durable low in cost and suitable for data which are not frequently accessed
Coldline: Suitable for backup 
Archive: Designed for long term preservation of data

|Storage Class   |Access Frequency          |Minimum Storage Duration   |
|----------------|--------------------------|---------------------------|
| Standard       | High-frequency access    | None                      |   
| Nearline       | less than once a month   | 30 days                   |   
| Coldline       | less than once a quarter | 90 days                   |
| Archive        | less than once a year    | 365 days                  |

The storage class not only sets the differentiator on object access frequency, but it also changes the minimum storage duration. Minimum storage capacity is also used to decide the charges for the storage.

**Pricing**
Google Cloud Storage is available for a low monthly fee based on the amount of data you store. Storage and bandwidth usage are calculated in gigabytes (GB), where: 1 GB = 230 bytes. For more information on pricing and special offers, visit http://code.google.com/apis/storage/docs/pricingandterms.html. 
