# Types of DBMS

Online transaction processing (OLTP) databases focus on recording Update, Insertion, and Deletion data transactions. OLTP queries are simple and short, which requires less time and space to process. A great example of an OLTP system is a bank ATM, in which you can modify your bank account using short transactions. 

Online analytical processing (OLAP) databases store historical data that has been input by OLTP. OLAP databases allow users to view different summaries of multidimensional data. Using OLAP, you can extract information from a large database and analyze it for decision-making. A good example of an OLAP system is a business intelligence tool.


# RDS

![RDS](images/rds.JPG)


## Configuring DB in a VPC

[Working with a DB instance in a VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceinaVPC.html)

[RDS for Developer](https://aws.amazon.com/rds/resources/)

[Quick Demo](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1663495200/2HKpYD8YqBZB2VPPwyILrQ/tincan/e92d27afbf892bd9807456c5d88e791f486908d4/assets/w3gfFxG5PJwmj9JB_transcoded-M0j_riHCi1_zuvc0-rds-demo.mp4)


## RDS Security

The best practice is to restrict access to your database by placing it inside of an Amazon Virtual Private Cloud, or VPC. Now smetimes you may need to accept requests directly from the internet. In this case, you should create an internet gateway

Security groups are used to control access to a database instance. Amazon RDS can use three types of security groups: database, VPC, and EC2. Amazon RDS uses AWS Identity and Access Management, or IAM, to create and manage credentials. The same users and roles that you have in IAM can also be used with Amazon RDS. Amazon RDS requires both authentication and permission to access tables and data. IAM policies assign permissions that determine who can manage Amazon RDS resources

Third, securing communications to and from the database instance. This is known as data in transit. This is accomplished by using HTTPS connections. These connections are encrypted using Secure Sockets Layer, or SSL.

Finally, protecting data in the database. This is known as data at rest. Amazon RDS uses the industry-standard AES-256 bit encryption algorithm to encrypt the data while at rest

## RDS Aurora

1. Can create upto 15 Read Replicas. Can help in failure over as well.
2. Auto switch to healthy DB instance in-case of db failure without any data loss
3. Aurora is efficient compared to mysql or pgsql because of re-engineering of Log structured distrubuted storage layer (storage method)
4. Aurora stores 6 copies of your data in 3 AZs
5. encryption at rest and transit is available
6. Also it comes with isolation

### RDS Aurora Billing model

1. Aurora comes with 3 pricing model with type of hosting ondemand, Reserved (1-3 years contract), serveless based on capacity
2. Storage cost is Storage per gb per month
3. traffic cost is Input i/o per million request
4. backup cost is User initiated backup per gb per month
5. Data transferred to other AWS region or to outbound internet
6. No cost within same Region or same VPC

### Aurora Config

Database instance class

1. Memory optimized standard uasge - general production usage
2. Brustable is best for High pick

Read Replicas

1. Global Database available for Aurora mysql
2. Global Aurora database expand aurora database instance to multiple AWS Regions, with latency less than second


Security

1. AES 256 encryption algo to store and during backup also ( Encryption at rest )
2. Security group
3. IAM to create/manage credential

Monitoring

1. Aurora logs to CloudWatch
2. CloudWatch Log to S3 and then run analysis with AWS Athena  ( Athena provide interactive query on S3 )
3. Or CloudWatch Log to AWS ElasticSearch and then run analytics on AWS QuickSight ( QuickSight is BI tool )


Demo

[Quick Aurora Demo](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1663495200/2HKpYD8YqBZB2VPPwyILrQ/tincan/e92d27afbf892bd9807456c5d88e791f486908d4/assets/_yDm0RFgAof0_0zi_transcoded-OTLI6tcZvs6YlhUo-amazon-aurora-demo.mp4)


Developer

[Developer Doc](https://aws.amazon.com/rds/aurora/resources/?ar-cards-aurora.sort-by=item.additionalFields.dateAdded&ar-cards-aurora.sort-order=desc)


## Maintenance Window of RDS

Resolution
Note: If you receive errors when running AWS Command Line Interface (AWS CLI) commands, make sure that you’re using the most recent AWS CLI version.

Occasionally, AWS performs maintenance to the hardware, operating system (OS), or database engine version for a DB instance or cluster. For more information, see Maintaining a DB instance and Upgrading a DB instance engine version.

For information about pending maintenance events for your Amazon RDS DB instances, check the Events pane of the Amazon RDS console. Then, check for engine-specific maintenance events. You can run describe-pending-maintenance-actions using the AWS Command Line Interface (AWS CLI) or the Amazon RDS API for DescribeDBInstances. You can also check Amazon RDS recommendations for Pending maintenance available.

Hardware maintenance
Before maintenance is scheduled, you receive an email notification about scheduled hardware maintenance windows that includes the time of the maintenance and the Availability Zones that are affected. During hardware maintenance, Single-AZ deployments are unavailable for a few minutes. Multi-AZ deployments are unavailable for the time it takes the instance to failover (usually about 60 seconds) if the Availability Zone is affected by the maintenance. If only the secondary Availability Zone is affected, then there is no failover or downtime.

OS maintenance
After OS maintenance is scheduled for the next maintenance window, maintenance can be postponed by adjusting your preferred maintenance window. Maintenance can also be deferred by choosing Defer Upgrade from the Actions dropdown menu. To minimize downtime, modify the Amazon RDS DB instance to a Multi-AZ deployment. For Multi-AZ deployments, OS maintenance is applied to the secondary instance first, then the instance fails over, and then the primary instance is updated. The downtime is during failover. For more information, see Maintenance for Multi-AZ deployments.

DB engine maintenance
Upgrades to the database engine level require downtime. Even if your RDS DB instance uses a Multi-AZ deployment, both the primary and standby DB instances are upgraded at the same time. This causes downtime until the upgrade is complete, and the duration of the downtime varies based on the size of your DB instance. For more information, see the section for your DB engine in Upgrading a DB instance engine version.

Note: If you upgrade a SQL Server DB instance in a Multi-AZ deployment, then both the primary and standby instances are upgraded. Amazon RDS performs rolling upgrades, so you have an outage only for the duration of a failover. For more information, see Multi-AZ and in-memory optimization considerations.
