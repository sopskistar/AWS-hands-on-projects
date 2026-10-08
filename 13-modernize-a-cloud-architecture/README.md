# 13: Modernize a Cloud Architecture (Challenge Lab)

## Overview
Refactoring and securing a multi-tier cloud application architecture to achieve high availability, fault tolerance, secure inter-VPC routing, and least-privilege IAM and database access control[cite: 41, 42].

## Architecture Diagram
![Architecture Diagram](./architecture-diagram.png)

## Key Implementation Steps
1. **RDS Multi-AZ:** Modified the relational database instance from Single-AZ to Multi-AZ deployment by provisioning a standby replica for automated failover[cite: 41, 42].
2. **Database Security Group:** Secured MySQL database traffic (Port 3306) by restricting inbound access exclusively to the App Tier Security Group[cite: 41, 42].
3. **DynamoDB Activity Log:** Provisioned a NoSQL DynamoDB table named `ActivityLog` with a string partition key (`activityId`) and added initial audit items[cite: 41, 42].
4. **VPC Peering Return Routing:** Updated application private subnet route tables with return routes targeting the corporate VPC CIDR via the active VPC peering connection[cite: 41, 42].
5. **Multi-AZ Application Scaling:** Configured Auto Scaling Group subnets across multiple Availability Zones and scaled desired capacity to handle workloads[cite: 41, 42].
6. **IAM Role Permissions:** Attached the `AmazonDynamoDBReadOnlyAccess` managed policy to `AppRole` to grant secure read privileges to application backend workloads[cite: 41, 42].
