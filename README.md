
![Untitled Diagram-Page-2 drawio (3)](https://user-images.githubusercontent.com/82954458/158584023-c568e32d-8efc-4d05-bfa5-1bd3631cb3a2.png)



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



# Dev 

# vpc 
|Tags|VPC ID |IPv4 CIDR |
|------|---------|---------|
|dev-sample-vpc | vpc-02da433eebcaa87fc | 10.20.0.0/16 | 


# INSTANCE

## N. Virginia

|Tags |Instance ID|Instance type|Private IPv4 addresses |Subnet |
|------|---------|---------|
|dev-sample-0 | i-08423006f2b21c500 |t3.small | t3.small | subnet-0a6bb85d1d8ce2cb8 | 

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


 
