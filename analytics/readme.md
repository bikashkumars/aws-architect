# NoSQL DB and Analytics on AWS


## Key Value DB - Amazon DynamoDB

Amazon DynamoDB can handle more than 10 trillion requests per day and support peaks of more than 20 million requests per second. More than 100,000 AWS customers have chosen DynamoDB as their key-value database for mobile, web, gaming, ad tech, IoT, and other applications that need low-latency data access at any scale. DynamoDB supports ACID-compliant transactions.

ACID compliance ( Fully consistant )

Auto Scale In and Out.

It offers 2 types of consistency model

- Eventually consistent - where write speed if fast but you may see old record
- Consistent - Where speed is slow, but always you will get latest record

It's coming under serverless category

Define the unique partition key and then define the sort key

DynamoDB is Billed based on Read, Write and Storage we use.

Amazon DocumentDB is a fast, reliable, and fully managed database service that allows you to set up, operate, and scale MongoDB-compatible databases in the cloud. With Amazon DocumentDB, you can run the same application code and use the same drivers and tools that you use with MongoDB.

Amazon DocumentDB is used for storing semistructured data as a document, rather than normalizing data across multiple tables, each with a unique and fixed structure, as in a relational database. Documents stored in a document database use nested key-value pairs to provide the document's schema.

[Quick Demo](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1663524000/BLtzY3mMqfIyA2bFxyTBBQ/tincan/e92d27afbf892bd9807456c5d88e791f486908d4/assets/Qs5xp56YQkInMzEK_transcoded-prR_1_V1YOt0GyVG-dynamo-db-demonstration.mp4)

[Documentation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)

## GraphDB - Amazon Neptune

Amazon Neptune is a fast, reliable, fully managed graph database service that makes it easy to build and run applications that work with highly connected data sets used to discover potential fraudulent behavior before it happens. This starts with finding interactions between products, locations, and devices and then mapping those data points to individual users, customers, and/or employees.

Neptune graph use cases include recommendation engines, fraud detection, knowledge graphs, drug discovery, and network security.


## DocumentDB - Amazon DocumentDB

Amazon DocumentDB is a fast, reliable, and fully managed database service that allows you to set up, operate, and scale MongoDB-compatible databases in the cloud. With Amazon DocumentDB, you can run the same application code and use the same drivers and tools that you use with MongoDB.

Amazon DocumentDB is used for storing semistructured data as a document, rather than normalizing data across multiple tables, each with a unique and fixed structure, as in a relational database. Documents stored in a document database use nested key-value pairs to provide the document's schema.


## MemoryDB - Amazon ElasticCache

MemCache or Redis solution

[Demo](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1664031600/zwBM_iRSX_ZSnfV7NvPAAg/tincan/2490ab78cd22d8fbba8e2c0436e0a9ed2c41d3fe/assets/H6XZowJAvHzQnhCk_transcoded-Yx7FXALTDpIfss4d-elasti-cache-demonstration.mp4)

There are three common types of data caches: built-in, application, and remote. A remote cache is a centralized, in-memory repository that can dramatically improve the responsiveness of databases and applications. It stores data externally from the database in a non-relational key-value database. ElastiCache is a remote cache engine and supports the two most common open source caching engines: Memcached and Redis.

Two common approaches to caching are lazy loading and write-through. Lazy loading is reactive. Data is put into the cache the first time it is requested. Write-through is proactive. Data is put into the cache at the same time it is put into the database.

Now that we have covered important terms, let’s talk about security. Access control and authentication for ElastiCache are managed through AWS Identity and Access Management, or IAM. ElastiCache clusters are created within Amazon Virtual Private Cloud (Amazon VPC) and managed through VPC security groups.

On-premises servers can use ElastiCache provided that there is connectivity between your VPC and data center through either a VPN or AWS Direct Connect.

ElastiCache for Redis supports encryption at rest and in transit. Using the Redis AUTH feature, ElastiCache can also authenticate clients. This version of ElastiCache has versions that are compliant with HIPAA, FedRAMP, and PCI DSS.

Couple examples of how ElastiCache can be pared with other AWS services.

For example, WordPress is a popular open source content management system. WordPress stores content inside a database, usually MySQL. When a user comes to a website, the web server does a significant amount of work. It needs to query the database for page content, merge this content with a template file, apply the appropriate style sheet and JavaScript code, and then send the resulting HTML to the browser. Using ElastiCache allows web servers to do some of this work only once by gathering data from the cache instead of returning to the web server.

Let’s look at one more example. When websites become popular, servers get busy, and this slows down the website. One way to limit the burden on individual web servers is to store the sessions in a remote cache like ElastiCache.

This architecture begins with two Amazon EC2 web servers configured in an Auto Scaling group. Next is Elastic Load Balancing, which is configured to distribute traffic between the web servers. Now remember the session data is centrally stored by ElastiCache, meaning that data is immediately available to other web servers. If one server becomes overwhelmed, any other ElastiCache server can easily provide the session data.

Dream11 is India’s number one fantasy sports platform with over 14 million users in South Asia. The company has been using ElastiCache for Redis to support fantasy games including cricket and soccer. Dream11 has a peak demand of 1.5 million requests per minute and workloads that can quickly surge ten-fold. ElastiCache provides scaling on demand without downtime.

KeptMe is a Hong Kong-based company that provides teachers and parents with a cloud-based platform they can use to collaborate on a child’s educational development. An ElastiCache instance running Redis retrieves and stores information that customers frequently access. This also means that frequently accessed data is available offline, ensuring that users can access 85 to 90 percent of KeptMe’s full functionality, even when they don’t have an internet connection. Amazon Simple Storage Service (Amazon S3) stores media assets such as photos, videos, and audio files.

## Ledger DB

Amazon QLDB is a Ledger DB

Amazon Quantum Ledger Database (Amazon QLDB) is a ledger database that is purpose-built for customers who need to maintain a complete and verifiable history of data changes in an application. Amazon QLDB offers history, immutability, and verifiability combined with the familiarity, scalability, and ease of use of a fully managed AWS database. Amazon QLDB is a new class of database that eliminates the need to engage in the complex development effort of building your own ledger-like applications.

Amazon QLDB has a built-in, immutable journal that stores an accurate and sequenced entry of every data change. The journal is append-only, meaning that data can only be added to a journal, and it cannot be overwritten or deleted. This ensures that your stored change history cannot be deleted or modified.

Even if you delete the data from your ledger, you can still access the change history of that data by reading from the immutable journal. With Amazon QLDB, you can access the entire change history of your application’s data. You can query a summary of historical changes and also specific details related to transaction history.

Amazon QLDB uses a cryptographic hash function (SHA-256) to generate a secure output file of your data’s change history, known as a digest. The digest acts as proof of your data’s change history, allowing you to look back and validate the integrity of your data changes.



