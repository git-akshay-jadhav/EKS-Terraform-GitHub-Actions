# EKS Terraform GitHub Actions

Infrastructure as Code project for provisioning Amazon EKS with Terraform and validating infrastructure workflow through GitHub Actions.

This repository is designed as an interview-ready DevOps project because it connects AWS, Terraform, Kubernetes, and CI/CD into one practical infrastructure workflow.

## What This Project Demonstrates

- Terraform-based AWS infrastructure provisioning
- Amazon EKS cluster setup concepts
- GitHub Actions workflow for IaC validation
- Terraform `init`, `validate`, `plan`, and controlled `apply`
- IAM, VPC, node group, and Kubernetes infrastructure understanding

## High-Level Architecture

```text
Developer
   |
   v
GitHub Repository
   |
   v
GitHub Actions
   |
   v
Terraform Init / Validate / Plan
   |
   v
AWS Resources
   |
   v
Amazon EKS Cluster
   |
   v
Kubernetes Workloads
```

## Tech Stack

| Area | Tools |
|---|---|
| Cloud | AWS, EKS, IAM, VPC |
| Infrastructure as Code | Terraform |
| CI/CD | GitHub Actions |
| Containers | Docker, Kubernetes |
| Version Control | Git, GitHub |

## Repository Structure

| Path | Purpose |
|---|---|
| `.github/` | GitHub Actions workflow definitions |
| `eks/` | EKS-related Terraform configuration |
| `module/` | Reusable Terraform module structure |
| `Jenkinsfile` | Optional Jenkins-based workflow reference |
| `assets/` | Project images or reference assets |

## Typical Workflow

1. Update Terraform configuration.
2. Commit and push changes.
3. GitHub Actions validates Terraform syntax and formatting.
4. Terraform plan shows expected infrastructure changes.
5. Apply is performed only after review/approval.
6. EKS cluster is validated with `kubectl`.

## Useful Commands

```bash
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
```

Validate EKS access:

```bash
aws eks update-kubeconfig --region <region> --name <cluster-name>
kubectl get nodes
kubectl get pods -A
```

## GitHub Actions Secrets

Common secrets required for AWS-backed Terraform workflows:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_REGION
```

For production usage, prefer OIDC-based role assumption instead of long-lived access keys.

## Troubleshooting Checklist

- AWS credentials or OIDC role not configured correctly
- IAM role missing required permissions
- Terraform backend/state not configured correctly
- VPC/subnet configuration does not satisfy EKS requirements
- EKS node group stuck during creation
- Region mismatch between AWS CLI, Terraform provider, and GitHub secrets
- `kubectl` context not updated after cluster creation

## Interview Talking Points

- Why Terraform is used for repeatable infrastructure
- Difference between `terraform plan` and `terraform apply`
- Why Terraform state is important
- How GitHub Actions improves IaC review and validation
- IAM permissions needed for infrastructure automation
- EKS components: cluster, node group, VPC, subnets, security groups
- How to troubleshoot failed Terraform or EKS creation

## Learning Outcome

This project shows a real DevOps infrastructure workflow: source-controlled Terraform, automated validation, AWS infrastructure provisioning, and Kubernetes cluster readiness for application deployments.
