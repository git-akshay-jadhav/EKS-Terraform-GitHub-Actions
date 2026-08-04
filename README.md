# EKS Terraform GitHub Actions

Hands-on DevOps project for provisioning an Amazon EKS cluster with Terraform and automating infrastructure workflow checks through GitHub Actions.

## Project Overview

This repository demonstrates how Infrastructure as Code and CI/CD practices can be used together to manage Kubernetes infrastructure on AWS. The goal of the project is to show a clear DevOps workflow: define infrastructure in Terraform, review changes safely, and use GitHub Actions to validate or trigger infrastructure operations.

## What This Project Shows

- AWS EKS cluster provisioning using Terraform
- Infrastructure as Code structure for repeatable cloud setup
- GitHub Actions workflow for automation
- AWS IAM and provider configuration basics
- Terraform plan/apply workflow understanding
- Kubernetes cluster readiness for application deployment

## Tech Stack

| Area | Tools |
|---|---|
| Cloud | AWS, EKS, IAM, VPC |
| IaC | Terraform |
| CI/CD | GitHub Actions |
| Containers | Docker, Kubernetes |
| Version Control | Git, GitHub |

## Suggested Architecture

```text
Developer
   |
   v
GitHub Repository
   |
   v
GitHub Actions Workflow
   |
   v
Terraform Init / Validate / Plan / Apply
   |
   v
AWS Infrastructure
   |
   v
EKS Cluster
```

## Typical Workflow

1. Update Terraform configuration.
2. Commit and push changes to GitHub.
3. GitHub Actions validates the Terraform code.
4. Terraform plan shows expected infrastructure changes.
5. Approved changes can be applied to AWS.
6. EKS cluster becomes available for Kubernetes workloads.

## Interview Talking Points

- Why Terraform state is important
- Difference between `terraform plan` and `terraform apply`
- How GitHub Actions helps avoid manual infrastructure mistakes
- How IAM permissions affect Terraform execution
- Why EKS needs VPC, subnets, node groups, and security groups
- How to troubleshoot failed Terraform or GitHub Actions runs

## Troubleshooting Notes

Common issues in this type of setup include:

- AWS credentials not configured correctly
- IAM user or role missing required permissions
- Terraform state lock or backend configuration issues
- EKS node group creation failures
- GitHub Actions secrets not configured correctly
- Region mismatch between Terraform provider and AWS resources

## Learning Outcome

This project helped me understand the relationship between Terraform, AWS EKS, and CI/CD automation. It is useful for DevOps interviews because it connects cloud infrastructure, Kubernetes, and automated delivery workflow in one practical example.
