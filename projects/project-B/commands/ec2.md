# EC2 Commands for Project B

## Table of Contents

- [Launching EC2 Instance](#launching-ec2-instance)
- [Connecting to Aurora MySQL from EC2](#connecting-to-aurora-mysql-from-ec2)
- [Resources](#resources)

## Launching EC2 Instance

```bash
#launch EC2 Instance
ssh -i /path/to/MyKeyPair.pem ec2-user@ec2-xx-xx-xx-xx.compute-1.amazonaws.com
```

## Connecting to Aurora MySQL from EC2

```bash
#Connecting to Aurora MySQL from EC2
mysql -h <Aurora_Endpoint> -u <username> -p
```

## Resources

- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [EC2 FAQs](https://aws.amazon.com/ec2/faqs/)
- [EC2 Instances.info](https://www.ec2instances.info/)
- [Spot Instances](https://aws.amazon.com/ec2/spot/)

## Additional Notes

- Always ensure that your EC2 instance and Aurora MySQL are within the same VPC or have the necessary VPC peering for communication.
- Avoid opening the MySQL port (3306) to the world; restrict access to only required IPs or security groups.
- Consider encrypting data in transit using SSL/TLS.

---

[Return to Project B Overview](../README.md)