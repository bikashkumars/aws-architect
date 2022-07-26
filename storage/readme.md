# AWS Storage

AWS Provides Block, file and Object Storage

![AWS core storage service](images/core_storage_service_aws.JPG)

## Block Storage

Block storage is raw storage in which the hardware storage device or drive is a disk or volume that is formatted and attached to the compute system for use. The storage is formatted into predefined continuous segments on the storage device. These segments are called blocks. The blocks are the basic fixed storage units used to store data on the device.

Storage devices can be hard disk drives (HDDs), solid state drives (SSDs), or newer types of storage devices, such as Non-Volatile Memory Express (NVMe). In addition to individual storage devices, you can deploy block storage on storage area network (SAN) systems.

The storage device is used by the operating system or an application that has the capabilities to manage block storage directly. For cases in which the application manages the block storage, the application often shares management with an operating system.

## File Storage

File storage is built on top of block storage, typically serving as a file share or file server. File storage is created using an operating system that formats and manages the reading and writing of data to the block storage devices. The name file storage comes from the primary use of storing data as files typically in a directory tree hierarchy.

The two most common storage protocols for file storage are Server Message Block (SMB) and Network File System (NFS). You can use the network protocols to communicate with remote computers and servers. You can also use server resources or share, open, and edit files.

The operating system manages the storage protocol and the operation of the file system. The file system can be Windows Server, Linux, or a specialized operating system used on network attached storage (NAS) devices or clustered NAS systems.

## Object Storage

Object storage is also built on top of block storage. Object storage is created using an operating system that formats and manages the reading and writing of data to the block storage devices. The name object storage comes from the primary use of storing the data within a binary object. Unlike file storage, object storage does not differentiate between types of data. The type of data or the file type becomes part of the data's metadata.

An object is made up of a larger set of blocks organized by using a predetermined size. For example, one object storage system uses binary object sizes of 128 megabytes (MB). Smaller files or data are stored at a binary level within the object. Larger data files are stored by spreading the data across multiple objects.

Object storage is recognized for its inherent availability of the file objects. Some systems support file versioning, file tracking, and file retention.

# EFS

![EFS usecase aws](images/aws_efs_usecase.JPG)

Amazon EFS is a scalable, elastic, cloud-native file system for Linux. Amazon EFS supports the Network File System (NFS) protocol.

Amazon FSx for Lustre is an AWS fully managed parallel file system built on Lustre for high performance computing (HPC) workloads. 

FSx for Lustre supports the Lustre POSIX-compliant protocol.

Amazon FSx for NetApp ONTAP is the NetApp ONTAP operating system implemented as a fully managed service. 

FSx for NetApp ONTAP support iSCSI for block storage, NFS protocol for POSIX-compliant access, and SMB protocol for Windows-compatible access.

Amazon FSx for OpenZFS is an AWS fully managed implementation of the Open Zettabyte File System (ZFS). 

FSx for OpenZFS supports NFS and SMB protocols for a wide range of application implementations. 

![EFS](images/efs.JPG)


Amazon EFS supports the Network File System version 4 (NFSv4.1 and NFSv4.0) protocol. The applications and tools that you use today work seamlessly with Amazon EFS. Multiple compute modules can access an Amazon EFS file system at the same time. These modules include include Amazon EC2, AWS Lambda, Amazon Elastic Container Service (Amazon ECS), and Amazon Elastic Kubernetes Service (Amazon EKS). Accessing compute services provides a common data source for workloads and applications running on more than one compute instance or container.

With Amazon EFS, you pay only for the storage used by your file system, with no minimum fee or setup cost. Amazon EFS offers a range of storage classes designed for different use cases. These include:

1. Simple interface through the AWS Management Console, the AWS Command Line Interface (AWS CLI), or the Amazon EFS API.
2. File system access semantics, such as strong data consistency and file locking. You can use Amazon EFS to control access to your file systems through Portable Operating System Interface (POSIX) permissions. 
3. Supports authentication, authorization, and encryption capabilities to help you meet your security and compliance requirements. 
4. Provides the throughput, input/output operations per second (IOPS), and low latency needed for a broad range of workloads. With Amazon EFS, you can choose from two performance modes and two throughput modes:

# EFS Usecase

![EFS Use](images/efs_usecase.JPG)

Amazon EFS provides a shared persistence layer that allows stateful applications to elastically scale up and down, such as for the following

1. DevOps
2. Web serving
3. Web content systems
4. Media processing
5. Machine learning
6. Analytics
7. Search index
8. Stateful microservices applications

![EFS Use](images/EFS_feature.JPG)


# EFS 

1. NFS protocol
2. NFS v4 version is followed by EFS
3. EFS allows file wise permission
4. file wise locking
5. Tree/directory structure
6. It can be connected to On-prim and EC2 and NFS drive. All can access parallel.
7. EFS is designed for linux
8. FSX is there for windows
9. 10 GB/second performance is granted
10. 10,000 I/O Ops is also available as part of performance
11. Storage space increases automatically, space is auto-scaled by AWS
12. EFS life cycle management allows less accessed file to moved low cost storage class for better cost optimization


# EFS Security

![EFS Use](images/efs_security.JPG)

1. From application, security can be implemented by IAM policy
2. From network security point of view, Security Group can be used to protect
3. Per appliation specific folder EFS Access point can be used to create folder and permission


# EFS Storage class

![EFS Use](images/efs_storage_class_types.JPG)

2 type of storage class provided by EFS
1. Standard Storage Class
2. Infrequent Access storage Class ( low cost )

File can be moved from standard to IA class by enabling life cycle management based on some date configured, file can be moved.

2 types of performance mode available by EFS

![EFS Operating mode](images/efs_mode.JPG)


You can start saving on your storage costs by enabling EFS lifecycle management for your file system and choosing an age-off policy of 7,14, 30, 60, or 90 days. With EFS lifecycle management policies enabled, files automatically move from Amazon EFS Standard storage to EFS Standard-IA storage, or from Amazon EFS One Zone storage to EFS One Zone-IA storage. Lifecycle management reduces storage costs by up to 92 percent.


## EFS Performance

Amazon EFS is designed to provide the throughput, IOPS, and low latency needed for a broad range of workloads. Throughput and IOPS scale as a file system grows. Throughput and IOPScan burst to higher throughput levels for short periods of time to support the unpredictable performance needs of file workloads. For the most demanding workloads, Amazon EFS can support performance over 10 GB/sec and over 500,000 IOPS.


## Other AWS service supporting EFS

Amazon EFS integrates with AWS containers and serverless compute services that require shared storage for latency-sensitive and IOPS-heavy workloads at any scale.

Amazon EFS provides applications running on Amazon ECS, Amazon EKS, AWS Fargate, and AWS Lambda, access to shared file systems for stateful workloads.

AWS DataSync – AWS DataSync is a managed data transfer service. Use this service to move data between on-premises storage and Amazon EFS. 

AWS Backup – AWS Backup is a fully managed backup service. Use this service to manage and automate backups of your Amazon EFS file systems centrally. AWS Backup reduces the need for costly, custom solutions and manual processes. The service goes beyond backing up Amazon EFS and centralizes the backup of data across other AWS services in the cloud and on premises. 

AWS Transfer Family – AWS Transfer Family provides fully managed support for file transfers directly into and out of Amazon EFS. AWS Transfer Family supports Secure File Transfer Protocol (SFTP), File Transfer Protocol over SSL (FTPS), and File Transfer Protocol (FTP).


# EFS real world

1. Assume your EC2 instances do have 1 security group
2. create a Security Group and allow type as NFS and source from EC2 security group name. Outbound as allow all.
3. Create a NFS and towards last step it will ask for mount
4. In the mount choose target AZ, target subnet, newly created security group as step-2


# EBS

![use-case EBS AWS](images/aws_ebs_use_case.JPG)

EBS volumes behave like raw, unformatted block devices. You can mount these block devices as EBS volumes on your EC2 instances. EBS volumes that are attached to an EC2 instance are exposed as raw block storage volumes that persist independently from the life of the instance. You can create a file system on top of these volumes or use them in any way you would use a block device (such as a hard drive). You can dynamically change the configuration of a volume attached to an EC2 instance, unlike traditional disk drives that come in fixed sizes.

You can choose from different EBS volume types to balance optimal price and performance. You can achieve single-digit millisecond latency for high-performance database workloads, such as SAP HANA, or gigabyte-per-second throughput for large, sequential workloads such as Apache Hadoop. You can change EBS volume types, tune performance, or increase volume size without disrupting your critical applications. Amazon EBS provides you cost-effective block storage when you need it.

Amazon EBS provides multiple volume types that you can use to optimize storage performance and cost for a broad range of applications. These volume types are divided into two major categories: SSD-backed storage for transactional workloads, such as databases, virtual desktops, and boot volumes, and HDD-backed storage for throughput-intensive workloads, such as MapReduce and log processing. 

1. SSD-based volumes include two levels to meet your application requirements: General Purpose SSD volumes and Provisioned IOPS SSD volumes.

2. General Purpose SSD volumes (gp3 and gp2) balance price and performance for transactional applications, including virtual desktops, test and development environments, and interactive gaming applications.
3. Provisioned IOPS SSD volumes are the highest performance EBS volumes (io2 and io1) for your most demanding transactional applications, including SAP HANA, Microsoft SQL Server, and IBM DB2.


1. HDD-based volumes include Throughput Optimized HDD (st1) for frequently accessed, throughput-intensive workloads and the lowest cost Cold HDD (sc1) for less frequently accessed data.

## EBS pricing

With Amazon EBS, you pay only for what you use. Pricing for EBS volumes is based on the volume type, provisioned volume size, and the provisioned IOPS and throughput performance. EBS volume pricing varies based on the Availability Zone where it resides. The pricing for Amazon EBS snapshots is based on the actual amount of storage space that you use.


# AWS S3

Amazon S3 provides industry-leading performance for cloud object storage. Amazon S3 supports parallel requests. This means that you can scale your S3 performance by the factor of your compute cluster, without customizing your application. Performance scales per prefix, so you can use as many prefixes as you need in parallel to achieve the required throughput. You can have a virtually unlimited number of prefixes. Amazon S3 performance supports at least 3,500 requests per second to add data and 5,500 requests per second to retrieve data. Each S3 prefix can support these request rates, making it simple to increase performance significantly.

Amazon S3 provides strong read-after-write consistency for PUT and DELETE actions on objects in your Amazon S3 bucket in all AWS Regions. This applies to both writes to new objects and PUT actions that overwrite existing objects and DELETE actions. In addition, read operations on Amazon S3 Select, Amazon S3 access control lists, Amazon S3 object tags, and object metadata (for example, HEAD object) are strongly consistent.

Amazon S3 offers a range of storage classes designed for different use cases. Every S3 storage class supports a specific data access level at corresponding costs or geographic location. S3 storage classes include:

1. S3 Standard for general-purpose storage of frequently accessed data
2. S3 Standard-Infrequent Access (S3 Standard-IA) for less frequently accessed data
3. S3 One Zone-Infrequent Access (S3 One Zone-IA) for less frequently accessed data and lower availability requirements
4. S3 Intelligent-Tiering for data with unknown or changing access patterns
5. Amazon S3 Glacier Instant Retrieval for lower-cost archival storage that may require retrieval at any time.  
6. Amazon S3 Glacier Flexible Retrieval for low-cost archival storage with retrieval time from minutes to hours
7. Amazon S3 Glacier Deep Archive (S3 Glacier Deep Archive) for lowest-cost storage with retrieval times up to 12 hours
8. Amazon S3 on Outposts for on-premises hybrid data storage and satisfying data residency requirements. 


You can use Amazon Macie to discover and protect sensitive data stored in Amazon S3. Macie gathers a complete S3 inventory automatically and continually evaluates every bucket to alert on any of the following:

1. Any publicly accessible buckets
2. Unencrypted buckets
3. Buckets shared or replicated with AWS accounts outside of your organization 


## S3 Pricing

With Amazon S3, you pay for only what you use. No minimum fee applies. Amazon S3 has six cost components to consider when storing and managing your data: 

1. Storage pricing
2. Request and data retrieval pricing
3. Data transfer and transfer acceleration pricing
4. Data management and analytics pricing
5. Price to process your data with S3 Object Lambda
5. Amazon S3 pricing varies based on the AWS Region where it resides.