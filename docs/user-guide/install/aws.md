---
layout: docwithnav
assignees:
- ashvayka
title: Installing Thingsboard on AWS EC2 

---

* TOC
{:toc}

This guide describes how to install Thingsboard on AWS EC2 using public AWS AMIs.

##### Step 1. Choose AMI

Use one of the following links to start the installation:

 - [N. Virginia (us-east-1)](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#LaunchInstanceWizard:ami=ami-e73090f1)
 - [Ohio (us-east-2)](https://console.aws.amazon.com/ec2/v2/home?region=us-east-2#LaunchInstanceWizard:ami=ami-20705445)
 - [N. California (us-west-1)](https://console.aws.amazon.com/ec2/v2/home?region=us-west-1#LaunchInstanceWizard:ami=ami-f580d995)
 - [Oregon (us-west-2)](https://console.aws.amazon.com/ec2/v2/home?region=us-west-2#LaunchInstanceWizard:ami=ami-2ea8274e)
 - [Canada (ca-central-1)](https://console.aws.amazon.com/ec2/v2/home?region=ca-central-1#LaunchInstanceWizard:ami=ami-2156eb45)
 - [Ireland (eu-west-1)](https://console.aws.amazon.com/ec2/v2/home?region=eu-west-1#LaunchInstanceWizard:ami=ami-1296bc74)
 - [Frankfurt (eu-central-1)](https://console.aws.amazon.com/ec2/v2/home?region=eu-central-1#LaunchInstanceWizard:ami=ami-3971a556)
 - [London (eu-west-2)](https://console.aws.amazon.com/ec2/v2/home?region=eu-west-2#LaunchInstanceWizard:ami=ami-01928765)
 - [Singapore (ap-southeast-1)](https://console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#LaunchInstanceWizard:ami=ami-8d8734ee)
 - [Sydney (ap-southeast-2)](https://console.aws.amazon.com/ec2/v2/home?region=ap-southeast-2#LaunchInstanceWizard:ami=ami-ce8e8cad)
 - [Seoul (ap-northeast-2)](https://console.aws.amazon.com/ec2/v2/home?region=ap-northeast-2#LaunchInstanceWizard:ami=ami-a89c4fc6)
 - [Tokyo (ap-northeast-1)](https://console.aws.amazon.com/ec2/v2/home?region=ap-northeast-1#LaunchInstanceWizard:ami=ami-097b2b6e)
 - [Mumbai (ap-south-1)](https://console.aws.amazon.com/ec2/v2/home?region=ap-south-1#LaunchInstanceWizard:ami=ami-a5bfcfca)
 - [São Paulo (sa-east-1)](https://console.aws.amazon.com/ec2/v2/home?region=sa-east-1#LaunchInstanceWizard:ami=ami-8d4829e1)


 
**NOTE** This AMIs are optimized for low memory instances, thus we do not recommend to use them for performance tests.
 
##### Step 2. Choose Instance Type

You can choose **any** instance type **except t1.micro and t2.nano**, since Thingsboard server and related third-party requires 1Gb of RAM.
This instruction is verified on t2.micro which is eligible for free tier.   

##### Step 3. Configure Instance

No specific configuration items here. You can leave this tab without changes or apply configuration that is specific to your use-case.

##### Step 4. Add Storage

Minimum 8 Gb of Storage is required. We recommend to have at least 50 if you plan to upload some data.

##### Step 5. Add Tags

No specific configuration items here. You can leave this tab without changes or apply configuration that is specific to your use-case.

##### Step 6: Configure Security Group

We recommend to create new security group, for example "Thingsboard". Configure following inbound rules:

| Type            | Protocol | Port Range | Source    |
|-----------------|----------|------------|-----------|
| HTTP            | TCP      | 80         | 0.0.0.0/0 |
| SSH             | TCP      | 22         | 0.0.0.0/0 |
| Custom TCP Rule | TCP      | 1883       | 0.0.0.0/0 |
| Custom UDP Rule | UDP      | 5683       | 0.0.0.0/0 |

##### Step 7: Review and launch your instance

Once instance is launched, please wait some time for services to boot up and open Administration UI in the browser using public DNS from instance details.

