# Corporate-CleverADS Abstract
The purpose of this application is to provide the client with a scalable CRM where they can
manage and configure their entire Advertising infrastructure and logic.

##  Goals

 -  Allowing real-time changes to active advertising agents.  
 - Provide a panoramic view of all configured advertising campaigns and respective
configurations.
-  Support sudden high increases of number of requests.

### Corporate-CleverADS Stakeholders
Stakeholders will be contacted by the order defined below using the contact methods defined
below.

Availability of the client resources ***must match*** the contracted SLA.
 | Name | Role | E-Mail | Telephone Number
| ----------- | ----------- |----------- |----------- |
|Bruno Mackay | CTO | ||

# Corporate-CleverADS Architecture

Corporate-CleverADS Overview

###  Description

The above diagram shows the architectural overview of the AWS infrastructure used for project.

![Untitled Diagram-Page-2 drawio (4)](https://user-images.githubusercontent.com/82954458/158649108-d5090820-4d5e-4aad-a193-b83cb2054708.png)



### Technology stack
- PHP 
- Nginx
- Mysel 
- AWS ECS

##  Corporate-CleverADS Compute (ECS)
As application is dockerized, ECS Fargate is used as a new relic .
### Scaling policies
Scaling policies are used to trigger provisioning/deprovisioning of running tasks, based on:

- CPU usage

After some time of the application running in production, the results show that memory usage is usually around 15% of usage per task and CPU usage metric is the best one to control the
scaling of the Cluster.Policies set on production environment:
- CPU usage policy - Scale up on 70% CPU usage on entire cluster, with 33% increase or 2
tasks at least.
- CPU usage policy - Scale down on 30% CPU usage on entire cluster, with 25% decrease or 1
task at least.

### Health Check
For checking the application health, a client-managed file health check.php is stored inside the root of the projects folder. This file is used for health checking on both using AWS Application Load Balancer and CloudFlare’s Global Load Balancer.


Health Check path:
- staging: *http://staging.samplesource.com/*
- production: *http://samplesource.com/*


# Prod

# VPC 

|Tags|VPC ID |IPv4 CIDR |
|------|---------|---------|
|Live-sample-vpc| vpc-0d105626b5933a035 | 10.10.0.0/16 |

# INSTANCE

## N. Virginia

|Tags |Instance ID|Instance type|Private IPv4 addresses |Subnet|
|------|---------|---------|--------|--------|
|Prod-sample-as|i-0196be6fb710aa724 |c5.xlarge |10.10.57.188 |subnet-0baad8304b1f54f02 |
|Prod-sample-0 |i-02f15cf64a9ad1be2 | t3.small | 10.10.1.129 |subnet-01068cf8ad487b3e0 |
|Prod-sample-as| i-0500be3d25ae9b0bf |c5.xlarge| 10.10.76.44 | subnet-0ca156edb893f6ca1| 
|Prod-sample-as | i-0502d1d6ea448ed28 | c5.xlarge | 10.10.16.187 | subnet-01068cf8ad487b3e0 |
|Prod-sample-as | i-0737fb024c5eb0678 | c5.xlarge |10.10.33.106 | subnet-0baad8304b1f54f02 |

## SECURITY GROUPS

|Tags|Security groups|
|------|---------|
|prod-sample | sg-0784c4a29214157cd | 

## Elastic File System

|Tags |File system ID |Security group ID |
|------|---------|---------| 
|Prod-sample |fs-0f8d8bfb3ed9d2a1f | sg-04a05b0f687e58da2 | 

## RDS 

###  Prod-sample

|DB identifier |Region & AZ |size |
|------|---------|--------|
| Prod-reader-1 | us-east-1a |db.r5.xlarge|
| Prod-reader-2 |us-east-1b|db.r5.xlarge| 
| prod-sample-1 |us-east-1c|db.r5.xlarge |

## LOAD BALANCER

|Tags |DNS name |ARN |
|------|------|------|
|sample-prod | sample-prod-405451511.us-east-1.elb.amazonaws.com | arn:aws:elasticloadbalancing:us-east-1:274086747439:loadbalancer/app/sample-prod/f87b0a1478121607 |

# Dev 

# VPC
|Tags|VPC ID |IPv4 CIDR |
|------|---------|---------|
|dev-sample-vpc | vpc-02da433eebcaa87fc | 10.20.0.0/16 | 


# INSTANCE

## N. Virginia

|Tags |Instance ID|Instance type|Private IPv4 addresses |Subnet |
|------|---------|---------|---------|---------|
|dev-sample-0 | i-08423006f2b21c500 |t3.small | 10.20.14.211 | subnet-0a6bb85d1d8ce2cb8 | 

## SECURITY GROUPS

|Tags|Security groups|
|------|---------|
| dev-sample  |  sg-06c4c95a42d83fe03 |

## Elastic File System

|Tags |File system ID |Security group ID |
|------|---------|---------| 
|dev-sample |fs-0375f92c332295174| sg-026fb0d0f2c296640 | 

## RDS 

###  Dev-sample

|DB identifier |Region & AZ | size |
|------|---------|--------|
|dev-sample-1 | us-east-1c| db.t3.small |
 
 ## LOAD BALANCER

|Tags |DNS name |ARN |
|------|------|------|
|sample-dev|sample-dev-1822065155.us-east-1.elb.amazonaws.com|arn:aws:elasticloadbalancing:us-east-1:274086747439:loadbalancer/app/sample-dev/5c86d00f1181a934| 

