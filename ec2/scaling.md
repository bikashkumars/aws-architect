# What to take care When auto-scaling is configured

Goto Auto Scaling Group and Edit, then configure following in Autoscaling group in Suspended Processes

* Launch
* Terminate
* Health check
* Replace unhealthy
* Schedule Action

During the AMI-creation process, Amazon EC2 creates snapshots of your instance's root volume and any other EBS volumes attached to your instance. You're charged for the snapshots until you deregister the AMI and delete the snapshots. If any volumes attached to the instance are encrypted, the new AMI only launches successfully on instances that support Amazon EBS encryption.


You can copy an Amazon Machine Image (AMI) within or across AWS Regions. You can copy both Amazon EBS-backed AMIs and instance-store-backed AMIs. You can copy AMIs with encrypted snapshots and also change encryption status during the copy process. You can copy AMIs that are shared with you.
