# Creating a Private Subnet with Amazon VPC

## Introduction

In this project, we create a **secure, isolated network** within **AWS** using **Amazon VPC**. This involves setting up both **public and private subnets**, configuring **route tables**, and applying **network ACLs** to control access and ensure security.

## What is Amazon VPC?

Amazon **VPC (Virtual Private Cloud)** allows you to create a private network within AWS. It provides complete control over IP ranges, subnets, route tables, and security settings. VPC is useful for securely managing resources while controlling connectivity and network isolation.

## How I Used Amazon VPC in This Project

In today's project, I used **Amazon VPC** to:
- Create a **secure and isolated network** within AWS
- Set up **public and private subnets**
- Configure **route tables** for proper traffic flow
- Apply **network ACLs** to control access to resources and ensure secure communication

## Key Concepts and Steps

### Private vs Public Subnets

- **Public subnets** have direct internet access via an **Internet Gateway**.
- **Private subnets** are isolated and don't have direct internet access. They rely on a **NAT Gateway** or **VPN** for external communication, offering better security for sensitive resources.

### Dedicated Route Table

- By default, my private subnet is associated with the **main route table**, which allows local VPC traffic but no internet access.
- To enable secure external communication, I set up a **new route table** that routes traffic through a **NAT Gateway**.

### Network ACLs

- By default, private subnets use the **default Network ACL (NACL)**, which allows all inbound and outbound traffic.
- I created a **dedicated network ACL** to control inbound and outbound traffic more strictly, applying specific rules for better security.

## Project Steps

### 1. Create a Private Subnet
- Created a new subnet and assigned it a CIDR block that avoids overlap with the public subnet.

### 2. Create a Private Route Table
- Assigned the private subnet to a dedicated route table, ensuring no routing to the **Internet Gateway**.

### 3. Create a Private Network ACL
- Set up custom **network ACLs** that deny all traffic by default, with specific rules to control inbound and outbound traffic.

## Lessons Learned

- **Level of Detail**: Configuring route tables and network ACLs took more time than expected. The need to customize these settings for both security and traffic flow required careful planning.
- **Time**: The project took about **1 hour** to complete, including setting up VPC, subnets, route tables, and fine-tuning security settings.

## Summary

In this project, we learned how to:
- 🚷 **Create a private subnet**: Assigned a unique CIDR block.
- 🚧 **Create a private route table**: Ensured no internet gateway access for the private subnet.
- 🚔 **Create a private network ACL**: Applied custom security rules for inbound and outbound traffic.

## Conclusion

This project demonstrates how to securely manage AWS resources by leveraging **Amazon VPC** to create private subnets, configure routing and security, and ensure proper isolation and access control. This structure is essential for maintaining a secure cloud environment.
