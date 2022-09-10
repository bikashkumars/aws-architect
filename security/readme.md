# AWS Security

It's shared security model between AWS and You.


# AWS beyond Security Group and NACL

For following service, you can not restrict using Security group and Network Access Control List

Amazon Domain Name Services (DNS)

Amazon Dynamic Host Configuration Protocol (DHCP)

Amazon EC2 instance metadata

Amazon ECS task metadata endpoints


| Security group | Network ACL |
| --- | --- |
| Operates at the instance level | Operates at the subnet level |
| Applies to an instance only if it is associated with the instance | Applies to all instances deployed in the associated subnet (providing an additional layer of defense if security group rules are too permissive) |
| Supports allow rules only | Supports allow rules and deny rules |
| We evaluate all rules before deciding whether to allow traffic | We evaluate rules in order, starting with the lowest numbered rule, when deciding whether to allow traffic |
| Stateful: Return traffic is allowed, regardless of the rules | Stateless: Return traffic must be explicitly allowed by  |