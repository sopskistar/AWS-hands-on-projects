# 12: Highly Available Web Applications

## Overview
Designing and deploying a multi-AZ fault-tolerant web architecture by expanding an EC2 Auto Scaling Group across three Availability Zones behind an Application Load Balancer (ALB)[cite: 40].

## Architecture Diagram
![Architecture Diagram](./architecture-diagram.png)

## Key Implementation Steps
1. Configured an Application Load Balancer with HTTP health checks targeting backend EC2 instances across multiple Availability Zones[cite: 40].
2. Updated the Auto Scaling Group network configurations to span across three distinct Availability Zones (`us-east-1a`, `us-east-1b`, `us-east-1c`)[cite: 40].
3. Increased Desired and Minimum capacity limits to guarantee active multi-node distribution across target subnets[cite: 40].
4. Verified automated target registration within the ALB Target Group to ensure seamless load balancing and high availability against zone failures[cite: 40].
