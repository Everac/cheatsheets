# AWS Certified Solutions Architect Associate 2019 - Cheatsheet

A cheat sheet for the AWS Certified Solutions Architect Exam

## 📚 About the exam

- 130 minutes lenght
- 65 questions
- Results between 100 and 1000 - passing score = 720
- Qualification valid for 3 years

## 📚 Regions and Availability Zones

- 19 regions and 57 availability zones. 5 more regions and 15 more availability zones in 2019.

- 1 region = Geographical area which contains at least 2 Availability Zones. Example: Paris region has 3 availability zones, Ireland region has 3 availability zones.

- An Availability Zone (AZ) is one or more discrete data centers, each with redundant power, networking and connectivity, housed in separate facilities.

- Edge locations are endpoints in which AWS catch content. Typically this consists of Cloud Front, Amazon’s Content Delivery Network,  etc… Currently there are over 150 edge locations.

- VPC is a networking service.

## 📚 IAM

IAM allows you to manage users and their level of access to the AWS console.

IAM has the following features:

- Centralised control of your AWS account
- Shared Access to your AWS account
- Granular permissions
- Identity Federation (Facebook, Linkedin, etc… access)
- MFA (Multi Factor Authentification)
- Temporary access to users 
- Password Rotation Policy
- PCI DSS Compliance

Terminology:

- Users
- Groups
- Policies
- Roles

## 📚 S3

## 📚 EC2

## 📚 Databases

## 📚 Route53

## 📚 VPC

## 📚 HA Architecture

## 📚 Applications

## 📚 Serverless

## 💁‍♀️ Restore a snapshot as a new EC2 instance

**Create an AMI**
- Go to snapshots (EC2 -> Snapshots)
- Choose a snapshot
- Right click -> Create Image
- Give it a name and Description
- Hit Create

**Create an EC2 instance with the AMI**
- Go to Images -> AMIs
- Right click -> Luanch the AMI
- Choose the proper type (t2, t3a, t3, etc.) and choose a size
- Review and Launch

**SSH into instance**
- Connect using the .pem
- Might need to use `ubuntu` as the user name
- Existing DB credentials are same as orignal

## 🙏 Setup snapshot backups with AWS Backup
-coming soon

## 🥛 Upgrade an existing instance
Instructions for resizing an EC2 EBS-backed instance in AWS. This is the "quick and dirty way" of resizing. The better way is to create a new instance at the desired size, get it working, and then move over the meta data and A records.

Official docs:
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-resize.html#resize-ebs-backed-instance

EC2 Instance types:
https://aws.amazon.com/ec2/instance-types/

**Steps:**
- Stop the instance (right click -> Instance State -> Stop)
- Wait for it to stop
- Change instance type (right click -> Instance Settings -> Change Instance Type)
- Start instance (right click -> Instance State -> Start)
- Wait for new public IP address to appear
- (If using Forge) Add new IP address to metadata in Forge (Server Details -> Meta -> IP Address)
- Update A records in DNS (Cloudflare, etc.)
- Complete!

**Total time: 3-5 mins**

**Notes**
- Check server logs after
- Stop and start scheduler before and after to avoid errors
- Test web and mobile app 
- Test IP address of server to make sure propagation is complete

