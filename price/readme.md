# How AWS Charge

* All data coming from internet to AWS is free
* Internal Region communication is chargeable
* All outbound data are chargeable

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

## AWS tool to manage cost

### AWS Budget 
Set custom budgets that alert you when you exceed your budgeted thresholds.

If Cost Explorer don't have any billing data ( new account or no resource running case), then you will get following error in AWS budget tool, while creating customized budget.

Because Cost Explorer is not enabled for this account, AWS Budgets does not have access to your billing data. This limits the creation of some budget types and configuration options. To enable these options, either create a budget or enable Cost Explorer. Changes can take up to 24 hours to take effect

* Cost budget - Recommended
Monitor your costs against a specified dollar amount and receive alerts when your user-defined thresholds are met. Using cost budgets, the budgeted amount you set represents your expected cloud spend. For example, you can set a cost budget for a business unit and then add additional parameters such as the associated member accounts.

* Usage budget
Monitor your usage of one or more specified usage types or usage type groups and receive alerts when your user-defined thresholds are met. Using usage budgets, the budgeted amount represents your expected usage. For example, you can use a usage budget to monitor the usage of certain services such as Amazon EC2 and Amazon S3.

* Savings Plans budget
Track the utilization or coverage associated with your Savings Plans and receive alerts when your percentage drops below a threshold you define. Setting a coverage target lets you see how much of your instance usage is covered by Savings Plans, while setting a utilization target lets you see if your Savings Plans are unused or underutilized.

* Reservation budget
Track the utilization or coverage associated with your reservations and receive alerts when your percentage drops below a threshold you define. Setting a coverage target lets you see how much of your instance usage is covered by reservations, while setting a utilization target lets you see if your reservations are unused or underutilized. Reservation alerts are supported for Amazon EC2, Amazon RDS, Amazon Redshift, Amazon ElastiCache, and Amazon Elasticsearch reservations.

Price/charge for using AWS Budget: AWS Budgets lets you set custom cost and usage budgets that alert you when your budget thresholds are exceeded (or forecasted to exceed). You can also create budgets to track your aggregate Reservation and Savings Plans utilization and coverage metrics. You can monitor and receive notifications on your budgets free of charge.

In addition to budget monitoring, you can add actions to your budgets to control IAM and Service Control Policy permissions as well as AWS resources when thresholds are exceeded (or forecasted to exceed). Your first two action-enabled budgets are free (regardless of the number of actions you configure per budget) per month. Afterwards each subsequent action-enabled budget will incur a $0.10 daily cost.


###  AWS Cost Explorer 

Cost Explorer provides reporting, analytics and visualization capabilities that you can use to track and manage your AWS costs.
You will be able to see your spend data within 24 hours after you launch Cost Explorer for the first time.)
