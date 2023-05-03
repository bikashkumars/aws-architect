# Amazon Queue Service

Most frequent AWS services used by developers

## AWS SQS

2 types of SQS queues can be created

1. Standard
2. FIFO

We can not change the queue type once this is changed
maximum 256kb

Visibility timeout - Once one consumer consumes once message, for that visibility time, message will not be delivered to other consumer

Deadletter Queue - once a message receives maximum receive count, then that message will move to dead letter queue. Dead letter queue are normal queue. 
One SQS queue can be used as dead letter queue for multiple SQS.
