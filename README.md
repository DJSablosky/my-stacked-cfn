# Nested AWS CloudFormation templates

This repository contains three AWS CloudFormation templates.

The first template deploys a VPC, with a pair of public and private subnets
spread across two Availability Zones. It deploys an Internet Gateway, with a
default route on the public subnets. It deploys a pair of NAT Gateways (one in
each AZ), and default routes for them in the private subnets.

The second template creates a load balanced, Auto Scaled sample website in an
existing Virtual Private Cloud (VPC). This example creates an Auto Scaling
group behind a load balancer with a simple health check using a basic getting
start AMI that has a simple Apache Web Server-based PHP page. The web site is
available on port 80, however, the instances can be configured to listen on
any port (8888 by default).

The third template creates a stack from each of the first two
templates.  The Auto Scaling stack uses the output of the VPC stack for public
subnets.  An AWS key pair called "mykey" must exist for the nested stacks to
complete successfully, or the second template needs to be updated with the
appropriate AWS EC2 Key Name.

## CloudFormation templates

https://s3.amazonaws.com/cf-templates-djs-us-east-1/Onica_Nested_Stack.yaml

https://s3.amazonaws.com/cf-templates-djs-us-east-1/Onica_VPC.yaml

https://s3.amazonaws.com/cf-templates-djs-us-east-1/Onica_Autoscaling_Website.yaml
