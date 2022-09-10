# Instance Calculator

![EC2 Configuration](images/ec2_usage.JPG)

* On-Demand instance hours: 1977.0834
* 1977.0834 On-Demand instance hours x 0.0464 USD = 91.736670 USD
* On-Demand instances (monthly): 91.736670 USD


# EBS calculation

![EBS Configuration](images/ebs_usage.JPG)

* 1,977.0834 total EC2 hours / 730 hours in a month = 2.71 instance months
* 30 GB x 2.71 instance months x 0.10 USD = 8.13 USD (EBS Storage Cost)
* EBS Storage Cost: 8.13 USD
* Total snapshots: 3
* Initial snapshot cost: 30 GB x 0.0500000000 = 1.5 USD
* Monthly cost of each snapshot: 1 GB x 0.0500000000 USD = 0.05 USD
* Discount for partial storage month: 0.05 USD x 50% = 0.025 USD
* Incremental snapshot cost: 0.025 USD x 3 = 0.075 USD
* Total snapshot cost: 1.5 USD + 0.075 USD = 1.575 USD
* 1.575 USD x 2.71 instance months = 4.27 USD (total EBS snapshot cost)
* 8.13 USD + 4.27 USD = 12.40 USD (Total EBS cost)
* Amazon Elastic Block Storage (EBS) total cost (monthly): 12.40 USD