## IAM - Identity and Access Management
- IAM solves the Authentication and Authorization problem for an aws account
- IAM manages:
    - Users - We will create for authentication
    - Policies
    - Groups - To which a new person is added 
    - Rules - Similar to users but they are created for **temporary purposes** or to interact between 2 aws accounts (Users are meant to be created inside aws)

- Types of Users in aws:
    - Root Users - can do any thing Supreme, root user is created when you first create an AWS account
    - IAM Users - These are individual users you create within your AWS account using Identity and Access Management (IAM).
    - IAM Roles: IAM roles are similar to users, but they are meant to be assumed by anyone or anything that needs to access AWS resources. 

## EC2 - Elastic cloud compute 
- Compute means 
    - CPU
    - RAM
    - Disk
- EC2 means virtual server
- Unlike private cloud, we don't need to manage the updates, security, etc and EC2 is elastic (pay as you go)
### Types of EC2 Instances
- General
- Compute optimized - for ML and Gaming related projects
- Memory optimized - for Big data analytics related projects
- Storage optimized 
- Accelerated 

## VPC - Virtual Private Cloud
- Devops engineers will build the VPC
- we will ask for ip address range to aws for a particular vpc
- VPC will be configured by devops engineer so that it will have number of subnets and also public subnet
- A user will be connected to public subnet using **Internet Gateway** 
- We have Load Balancer, route-tables(route) to connect to private subnets
- We have this Security Group which ensures the security by checking the ip address
- NACL is automation for defining Security Groups
- NAT(Network Address Translation) Gateway used to interact private subnets with internet with masking the ip address(secure info)
- VPC Flow logs will record every action (which is Chargeable)
![alt text](<Screenshot 2025-05-18 193220.png>)

## Security Groups, NACL
- Security is a shared responsibility of both aws and companies(means devops and cloud engineers of the company)
- By default AWS VPCs come with a security group that will set inbound traffic to non and outbound traffic is open to all for all **except port 25** bcz AWS blocks outbound traffic on port 25 (SMTP) for EC2 instances and Lambda functions to prevent spam.
- NACL - Network Access Control List
- Security Group is at EC2 instance level and NACL is at subnet level
- SG we only have rules for allowing but in NACL we have allowing and denying rules
- Remember in NACL rules are applied by giving priority to top ones 

## Route 53
- It provides DNS as a service
- We have ip address to load balancer and applications inside a vpc but we never use them directly, we use Domain names instead which is basically converted into ip address by DNS (This ip address is *ip of the load balancer*)
- 2 reasons to use domain names 
    - Names are easy to remember than ip address
    - ip address can be dynamic for some applications