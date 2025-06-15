# aws-infrastructure-as-code

This repository contains AWS infrastructure as code for deploying and managing resources using CloudFormation and GitHub Actions.

## Workflows

[![Deploy to DEV/QA AWS](https://github.com/gogulamudigeethareddy/aws-infrastructure-as-code/actions/workflows/dev-qa-deploy.yaml/badge.svg?event=workflow_run)](https://github.com/gogulamudigeethareddy/aws-infrastructure-as-code/actions/workflows/dev-qa-deploy.yaml)
[![Deploy to PROD AWS](https://github.com/gogulamudigeethareddy/aws-infrastructure-as-code/actions/workflows/prod-deploy.yaml/badge.svg?branch=main&event=workflow_run)](https://github.com/gogulamudigeethareddy/aws-infrastructure-as-code/actions/workflows/prod-deploy.yaml)

## Structure

- [`rds/template.yaml`](rds/template.yaml): CloudFormation template for Aurora PostgreSQL RDS Cluster.
- [`oidc-provider/cloudformation-oidc.yaml`](oidc-provider/cloudformation-oidc.yaml): CloudFormation template for OIDC provider and IAM roles for GitHub Actions.
- [`.github/workflows/`](.github/workflows/): GitHub Actions workflows for CI/CD.

## Deployment

### OIDC Provider

Deploy the OIDC provider and IAM roles for GitHub Actions using the workflow:
- [`.github/workflows/oidc-provider.yaml`](.github/workflows/oidc-provider.yaml)

### RDS Cluster

Deploy the Aurora PostgreSQL RDS cluster using the workflow:
- [`.github/workflows/deploy-rds-dev.yaml`](.github/workflows/deploy-rds-dev.yaml) (for DEV)
- [`.github/workflows/dev-qa-deploy.yaml`](.github/workflows/dev-qa-deploy.yaml) (for DEV/QA)
- [`.github/workflows/prod-deploy.yaml`](.github/workflows/prod-deploy.yaml) (for PROD)

## Usage

1. Push changes to the appropriate branch (`develop` for DEV/QA, `main` for PROD).
2. Workflows will automatically deploy or update the infrastructure.

## Requirements

- AWS account with appropriate permissions.
- GitHub repository secrets configured for AWS roles and credentials.

---