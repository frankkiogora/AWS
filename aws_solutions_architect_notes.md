# AWS Solutions Architect Certification

* AWS Concepts 
* AWS Essentials
* AWS Solutions Architect
* Linux Essentials

**Certified Solutions Architect (CSA) Domains:**
1. Design highly available, cost-efficient, fault-tolerant, scalable systems
2. Implementation / Deployment
3. Data Security
4. Troubleshooting


******************************************************************************
## AWS Concepts

### INTRODUCTION

**High Availability** – files in the cloud are available from anywhere
**Fault Tolerant** – having multiple backups for file in case of system fault

**Enterprise Use of Cloud:**
1. Put servers (storage) off-site in cloud
2. Scaling upwards is easier because you only use servers in cloud that you need
3. Don’t have to estimate future server needs

**Scalability** – ability to quickly/easily add more servers
**Elasticity** – ability to shrink on-demand as needed


### UNDERSTANDING VPCs

**Virtual Private Cloud:**
1. Your private section of AWS
2. Can allow/restrict access to your VPC
3. Can put EC2 and RDS on your VPC


### UNDERSTANDING EC2

**Elastic Cloud Compute (EC2):**
1. Virtual server computer
2. EC2 acts as a web server for Netflix
3. Common use – Web Hosting, encoding, transcoding
4. Good for any type of processing activity
Instance – many times an EC2 computer is referred to as an “EC2 Instance”

### UNDERSTANDING RDS

**Relational Database Service (RDS):**
1. Place to store customer account info, inventory catalog
2. As user traffic increases, demands on DB increase therefore additional EC2 Instances are created


### UNDERSTANDING S3

**Simple Storage Service (S3):**
1. Unlimited storage bucket for files, photos, documents
2. Mass storage container, long-term storage
3. As user traffic increases, demands on DB increase therefore additional EC2 Instances are created


### AWS Global Infrastructure (Physical Setup)

**Multiple Regions**
1. Each region has “availability zones”, which are geographically separated, physical data centers
2. As user traffic increases, demands on DB increase therefore additional EC2 Instances are created


******************************************************************************
## AWS Essentials

### PROJECT OMEGA
https://www.lucidchart.com/documents/view/703f6119-4838-4bbb-bc7e-be2fb75e89e5/0

### IAM (Identity & Access Management)
1. manage users and their access to AWS accounts and services
2. Root user – user created when AWS account is created

**AWS Best Practices:**
1. When new AWS account is created, complete task listed in IAM under “Security Status”
2. MFA (Multi-Factor Authentication) should always be set on your “root” account
3. NEVER use your root account for day-to-day use

### VPC (Virtual Private Cloud)

**VPC Basics**
1. By default, a VPC is made for you when you create an AWS account.
2. VPC is conceptually similar to a home network
	a. Home Network: Internet -> Modem -> Router/Switch -> Firewall -> Devices
	b. VPC: Internet -> Internet Gateway -> Route Table -> NACL -? EC2 Instances

**Internet Gateways (IGW)**






















