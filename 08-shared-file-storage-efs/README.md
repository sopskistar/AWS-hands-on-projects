# 08: Shared File Storage with Amazon EFS

## Overview
Configuring Amazon Elastic File System (EFS) to provide serverless, fully managed, scalable network storage accessible across multiple Amazon EC2 instances residing in separate Availability Zones.

## Architecture Diagram
![Architecture Diagram](./architecture-diagram.png)

## Key Implementation Steps
1. Provisioned an Amazon EFS file system configured with NFSv4 network endpoints across distinct Availability Zones (`us-east-1a`, `us-east-1b`, `us-east-1c`).
2. Configured custom VPC Security Groups (`PetModels-EFS-1-SG`) to regulate inbound NFS traffic (port 2049) strictly from authorized application web servers.
3. Installed `amazon-efs-utils` and mounted the shared network drive to local `/data` mount points across three Linux EC2 instances using TLS encryption.
4. Validated concurrent multi-node file write operations by appending distinct server logs (`site A`, `site B`, `site C`) to a single shared file system log.
