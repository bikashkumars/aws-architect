# EFS

![EFS](images/efs.JPG)

# EFS Usecase

![EFS Use](images/efs_usecase.JPG)


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
