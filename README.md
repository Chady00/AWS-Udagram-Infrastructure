## Udagram AWS Infrastructure

Fully designing and implementing an AWS infrasturcture template and stack using Cloudformation, EC2 instances, Custom VPC , Gateways, WebTemplate, IAM Roles, and S3 Storage buckets.
This project involves designing and implementing an AWS infrastructure using CloudFormation. The infrastructure includes EC2 instances, a custom VPC, gateways, and S3 storage.
![Infrastructure Diagram](https://github.com/Chady00/AWS-Udagram-Infrastructure/assets/84717550/069ca322-58f2-49f7-ac62-3a83a2ccc879)

_CloudFormation Template_  
The CloudFormation template (udagram-infrastructure.yml) provided in the repository defines the AWS resources needed for the infrastructure. Below is an overview of the resources created.

## CloudFormation Template Overview

## EC2 Launch Template for Web Servers

`WebAppLaunchTemplate:`  
`Type: AWS::EC2::LaunchTemplate`

##### `... (Details in the code)`

## `IAM Role for EC2 Instances`

`WebAppInstanceRole:`  
`Type: AWS::IAM::Role`

##### `... (Details in the code)`

## `IAM Instance Profile`

`WebAppInstanceProfile:`  
`Type: AWS::IAM::InstanceProfile`

##### `... (Details in the code)`


![image](https://github.com/Chady00/AWS-Udagram-Infrastructure/assets/84717550/7372a0a2-582b-4e8d-90c2-9be9fc936b15)


## `Auto Scaling Group`

`WebAppGroup:`  
`Type: AWS::AutoScaling::AutoScalingGroup`

##### `... (Details in the code)`

## `Elastic Load Balancer`

`WebAppLB:`  
`Type: AWS::ElasticLoadBalancingV2::LoadBalancer`

##### `... (Details in the code)`

## `S3 Bucket`

`S3Bucket:`  
`Type: AWS::S3::Bucket`

##### `... (Details in the code)`

##### `... (Other resources such as Security Groups, Listeners, etc.)`

### _**Instructions**_

  
Creation Instructions  
Clone the Repository:

**bash**  
git clone https://github.com/Chady00/AWS-Udagram-Infrastructure.git  
cd AWS-Udagram-Infrastructure

cd starter  
Deploy CloudFormation Stack:

**bash**  
../create stack-name network.yaml network-parameters.json  
You can edit the create.bat file to replace the AWS with the region where you want to deploy the infrastructure.

**Monitor Stack Creation:**

**bash**  
aws cloudformation describe-stacks --stack-name UdagramInfrastructure --region   
Access Load Balancer URL:

After the stack creation is complete, retrieve the Load Balancer URL from the CloudFormation outputs section or the AWS Management Console.

**Deletion Instructions**  
Delete CloudFormation Stack:

**bash**  
../delete stack-name

**Monitor Stack Deletion:**

Monitor the stack deletion progress in the AWS CloudFormation console or use the following command:

**bash**  
Copy code  
aws cloudformation describe-stacks --stack-name UdagramInfrastructure --region   
**Clean Up:**

Ensure that all resources are properly deleted. If there are any issues with deletion, you may need to manually delete remaining resources.
