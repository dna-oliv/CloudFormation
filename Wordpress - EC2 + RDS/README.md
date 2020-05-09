# An EC2 Instance and RDS template for Wordpress automated deployment.

### This CloudFormation template launches:
    - 1 RDS Instance
    - 1 EC2 Instance
    - 1 Security Group
    - 1 DB Security Group.

It uses default VPC and subnets.

# Free Tier
The instances are not selectable in the CloudFormation::Interface, they are set to use t2.micro and db.t2.micro, so you won't pay to use if you're still eligible for Free Tier. However, delete the stack as soon as you don't need it anymore.

# Installed Packages
### The services/packages/applications deployed along the EC2 Instance are as follow:
    - Apache 2.4
    - PHP 7.3
    - PHP 7.3 mysqlnd
    - Wordpress (latest)
    - Astra Theme (latest)
    - Astra Plugin (latest)

CloudFormation doesn't check bash script errors. The stack will rollback after the counter time expires if it doesn't 
receive a success signal.
If you alter bash scripts the file **`"/var/log/cloud-init-output.log"`** can give you clues of what is happening.

**Important note:** This template serves as an example and for learning purposes, do not launch it on production servers as it doesn't handle security concerns.