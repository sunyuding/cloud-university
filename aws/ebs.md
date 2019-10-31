# Amazon Elastic Block Store (EBS)
- Three volume types:
    - General Purpose (SSD)
    - Provisioned IOPS (SSD)
    - Magnetic
- Persistent and customizable block storage for EC2 instances
- Replicated in the same Availability Zone
- Backup using Snapchots
- Easy and transparent Encryption
- Elastic volumes
- EBS volumes persist beyond the life of an EC2 instance

Check which EBS was attached to the instance.
```bash
$ lsblk
xvda ...
xvdb ...
```

```
$ mke2fs /dev/xvdb
$ sudo !!
```

Q. You need to take a snapshot of an Amazon Elastic Block Store(Amazon EBS) volume. How long will the volume be unavailable?
- The volume will be available immediately.

Q. To help prevent data loss due to the failure of any single hardware component, Amazon Elastic Block Storage (Amazon EBS) automatically replicates EBS volume data to which one of the following?
- Within the same **Availability Zone** in a region.