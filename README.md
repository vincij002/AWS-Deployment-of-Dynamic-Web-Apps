# Dynamic Web App Deployment on AWS using Terraform, Docker, Amazon ECR, and ECS

## Project Overview

This project aims to deploy a dynamic web application on Amazon Web Services (AWS) using various DevOps tools and practices. The deployment process leverages Terraform for infrastructure provisioning, Docker for containerization, Amazon Elastic Container Registry (ECR) for container image storage, and Amazon ECS for container orchestration.

## Prerequisites

Before starting the deployment process, ensure you have the following prerequisites in place:

- Generate SSH key pairs for secure connections.
- Add your public SSH key to your GitHub account.
- Create an IAM user in AWS with appropriate permissions.
- Create an S3 bucket for storing Terraform state.
- Create a DynamoDB table for locking Terraform state.

## Project Components

### Terraform Modules

1. **VPC Module**: Create a 3-tier VPC from scratch.
2. **NAT Gateway Module**: Provision NAT Gateway for your VPC.
3. **Security Groups Module**: Set up security groups for your VPC.
4. **RDS Module**: Deploy an RDS instance for your database.
5. **Amazon Certificate Manager (ACM) Module**: Manage SSL certificates for AWS resources.
6. **Application Load Balancer (ALB) Module**: Create a load balancer for your application.
7. **S3 Bucket Module**: Set up an S3 bucket for your application.
8. **Task Execution Role Module**: Create a task execution role for ECS tasks.
9. **ECS Cluster, Task Definition, and Service Module**: Deploy ECS cluster, task definition, and service.
10. **ECS Auto Scaling Group Module**: Set up an ECS auto scaling group for your application.
11. **Route 53 Module**: Configure Route 53 DNS records for your application.

### Deployment Process

1. **Creating and Cloning Terraform Infrastructure Code Repository**: Set up a repository for Terraform infrastructure code and clone it.
2. **Creating Terraform Provider**: Configure Terraform provider for AWS.
3. **Setting up Terraform Backend**: Configure Terraform backend for state management.

## Deployment Steps

Follow these steps to deploy the dynamic web application on AWS:

1. **Infrastructure Provisioning**:
    - Initialize Terraform.
    - Apply Terraform configuration for each module to provision AWS resources.

2. **Docker Containerization**:
    - Build Docker images for the web application and any required services.
    - Tag Docker images appropriately.

3. **ECR Image Repository Setup**:
    - Create an Amazon ECR repository to store Docker images.
    - Push Docker images to the ECR repository.

4. **ECS Service Deployment**:
    - Create ECS task definition for the web application.
    - Configure ECS service to run tasks using the task definition.
    - Associate the ECS service with the ALB for load balancing.

5. **DNS Configuration**:
    - Configure Route 53 DNS records to point to the ALB.

6. **SSL Certificate Setup**:
    - Request and validate SSL certificates using ACM.
    - Associate SSL certificates with the ALB for secure communication.

7. **Testing and Monitoring**:
    - Test the deployed application for functionality and performance.
    - Set up monitoring and logging for AWS resources using CloudWatch.

## Technologies Used
- CI/CD: GitHub Actions
- Cloud Services: AWS (Route 53, EC2, S3, ECR, ECS, DynamoDB, IAM, etc.)
- Infrastructure as Code: Terraform
- Containerization: Docker, Amazon Elastic Container Registry (ECR), Amazon Elastic Container Service (ECS)
- Version Control: Git, GitHub
- Scripting: Bash
- Credential Management: AWS Secrets Manager, GitHub Actions Repository Secrets

