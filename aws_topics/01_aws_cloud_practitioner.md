# Cloud Computing

## Types of cloud computing
* Infrastrucure as a service(IaaS)
* Provide building blocks for cloud IT
* Provides networking, computers, data storage space
* Highest level of flexibility
* Easy parallel with traditional on-premises IT
* Platform as a service(PaaS)
* Removes the need for your organization to manage the underlying   infrastructure
* Focus on the deployment and management of your applications
* Software as a service(SaaS)
* Completed product that is run and managed by the service provider

## Aws history
* launched in 2002
* Aws has 216 points of presensse (205 Edge Locations & || Regional caches) in 84 cities across 42 Countries.

 ![aws_topics](regionscope.PNG?raw=true "Title")

## AWS Regions
1. AWS has regions all around the world
2. Names can be us-east-l, eu-west-3...
3. A region is a cluster of data centers
4. Most AWS services are region-scoped

## AWS IAM user

```

# IAM Roles and services
* Some AWS service will need to perform action on our behalf
* To do so, we will assign permissions to AWS services with IAM roles
* EC instance is just like a virtual server.
* Commom roles
 1. EC instance roles
 2. Lambda function roles
 3. Roles for CloudFormation

## IAM security Tools
* IAM Credentails report(account-level)
  1. A report that lists all you account's users and the status of their various credentails

# IAM Access Advisor(user-level)
  1. Access advisor shows the service permissions granted to a user and when those services were last accessed
  2. You can use this information to revise your policies.

  # IAM Gudiliness & Best practice
  * Don't use the root account except for AWS account setup
  * One physical user = One aws user
  * Assign users to groups and assign permission to user
  * MFA is must
  * use access key fpor pragramatic acces
  * Never share IAm key and acces key

  ## Responsibily of IAM user
  * Users, groups, roles , policies managament and monitoring
  * MFA for all accounts
  * Don't share the access key or IAM user id


