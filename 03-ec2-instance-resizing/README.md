# 03: Vertical Scaling with Amazon EC2 Instance Resizing

## Overview
Demonstrating vertical scaling (scaling up) by changing an Amazon EC2 instance type from `t3.micro` to `m4.large` to accommodate higher compute and memory demands for an enterprise application.

## Architecture Diagram
![Architecture Diagram](./architecture-diagram3.png)

## Key Implementation Steps
1. Assessed resource limits on an existing EC2 scheduling system instance.
2. Safely stopped the running EC2 instance to permit hardware profile re-configuration.
3. Modified instance settings in the AWS Console to resize the compute tier to `m4.large`.
4. Verified successful configuration and vertical scaling capability.
