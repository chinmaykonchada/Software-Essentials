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