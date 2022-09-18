# NoSQL DB and Analytics on AWS


## Key Value DB - Amazon DynamoDB

Amazon DynamoDB can handle more than 10 trillion requests per day and support peaks of more than 20 million requests per second. More than 100,000 AWS customers have chosen DynamoDB as their key-value database for mobile, web, gaming, ad tech, IoT, and other applications that need low-latency data access at any scale. DynamoDB supports ACID-compliant transactions.

ACID compliance ( Fully consistant )

Auto Scale In and Out

It's coming under serverless category

Define the unique partition key and then define the sort key

DynamoDB is Billed based on Read, Write and Storage we use.

Amazon DocumentDB is a fast, reliable, and fully managed database service that allows you to set up, operate, and scale MongoDB-compatible databases in the cloud. With Amazon DocumentDB, you can run the same application code and use the same drivers and tools that you use with MongoDB.

Amazon DocumentDB is used for storing semistructured data as a document, rather than normalizing data across multiple tables, each with a unique and fixed structure, as in a relational database. Documents stored in a document database use nested key-value pairs to provide the document's schema.

[Quick Demo](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1663524000/BLtzY3mMqfIyA2bFxyTBBQ/tincan/e92d27afbf892bd9807456c5d88e791f486908d4/assets/Qs5xp56YQkInMzEK_transcoded-prR_1_V1YOt0GyVG-dynamo-db-demonstration.mp4)

## GraphDB - Amazon Neptune

Amazon Neptune is a fast, reliable, fully managed graph database service that makes it easy to build and run applications that work with highly connected data sets used to discover potential fraudulent behavior before it happens. This starts with finding interactions between products, locations, and devices and then mapping those data points to individual users, customers, and/or employees.

Neptune graph use cases include recommendation engines, fraud detection, knowledge graphs, drug discovery, and network security.


## DocumentDB - Amazon DocumentDB

Amazon DocumentDB is a fast, reliable, and fully managed database service that allows you to set up, operate, and scale MongoDB-compatible databases in the cloud. With Amazon DocumentDB, you can run the same application code and use the same drivers and tools that you use with MongoDB.

Amazon DocumentDB is used for storing semistructured data as a document, rather than normalizing data across multiple tables, each with a unique and fixed structure, as in a relational database. Documents stored in a document database use nested key-value pairs to provide the document's schema.


## MemoryDB - Amazon ElasticCache

MemCache or Redis solution