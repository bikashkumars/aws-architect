# AWS Security

It's shared security model between AWS and You.

# Security Group

1. A security group name must be unique within the VPC.
2. You can specify allow rules, but not deny rules.
3. When you first create a security group, it has an outbound rule that allows all outbound traffic from the resource.
4. When you associate multiple security groups with a resource, the rules from each security group are aggregated to form a single set of rules that are used to determine whether to allow access
5. Security Group is not just for EC2, but it can be attached to many
6. Security Group is stateful, that means if inbound is allowed and traffic enters the instance while returning with response back to client, no outbound rule is checked.

# NACL

1. A network ACL has inbound rules and outbound rules. Each rule can either allow or deny traffic
2. Custom VPC automatically comes with a modifiable default network ACL. By default, it allows all inbound and outbound IPv4 traffic and, if applicable, IPv6 traffic.
3. You can create a custom network ACL and associate it with a subnet. By default, each custom network ACL denies all inbound and outbound traffic until you add rules.
4. Each subnet in your VPC must be associated with a network ACL. If you don't explicitly associate a subnet with a network ACL, the subnet is automatically associated with the default network ACL.
5. You can associate a network ACL with multiple subnets. However, a subnet can be associated with only one network ACL at a time. When you associate a network ACL with a subnet, the previous association is removed.
5. Network ACLs are stateless, which means that responses to allowed inbound traffic are subject to the rules for outbound traffic 


# Exceptions using Security Group and NACL

Following traffic/services can not be restricted/controlled using either Security group or Network Access Control List ( NACL )

Amazon Domain Name Services (DNS)

Amazon Dynamic Host Configuration Protocol (DHCP)

Amazon EC2 instance metadata

Amazon ECS task metadata endpoints

# Compare NACL and Security Group

| Security group | Network ACL |
| --- | --- |
| Operates at the instance level | Operates at the subnet level |
| Applies to an instance only if it is associated with the instance | Applies to all instances deployed in the associated subnet (providing an additional layer of defense if security group rules are too permissive) |
| Supports allow rules only | Supports allow rules and deny rules |
| We evaluate all rules before deciding whether to allow traffic | We evaluate rules in order, starting with the lowest numbered rule, when deciding whether to allow traffic |
| Stateful: Return traffic is allowed, regardless of the rules | Stateless: Return traffic must be explicitly allowed by  |