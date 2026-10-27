# Reading 16: AWS Cloud Servers

## Overview

Cloud computing allows developers to host applications, store data, and run servers without maintaining physical hardware.

**Amazon Web Services (AWS)** provides cloud infrastructure for deploying and managing applications.

## Key Concepts

- **Cloud Computing:** Accessing computing resources over the internet.
- **Containers:** Isolated environments used to package and run applications.
- **EC2 (Elastic Compute Cloud):** Virtual servers hosted by AWS.
- **CDN (Content Delivery Network):** Distributes content across multiple locations to improve delivery speed.
- **Horizontal Scaling:** Adding more server instances to handle increased traffic.
- **Elastic Beanstalk:** An AWS service that simplifies application deployment and infrastructure management.

## WHY — Why Use Cloud Servers?

Cloud servers allow developers to:

- Deploy applications without purchasing physical servers.
- Scale resources as application demand increases.
- Make applications accessible over the internet.
- Automate application deployment and management.

## WHAT — What Is Elastic Beanstalk?

**AWS Elastic Beanstalk (EB)** simplifies deploying applications such as Node.js servers.

It manages infrastructure components, including EC2 instances and application deployment resources.

Deploying an application involves two main parts:

1. **Environment:** The infrastructure where the application runs.
2. **Application Code:** The source code deployed into that environment.

## HOW — Deploy a Node.js Application

### Option 1: AWS Console (GUI)

1. Open AWS Elastic Beanstalk.
2. Create a new application.
3. Select Node.js as the platform.
4. Prepare a ZIP file containing the application source code.
5. Upload the ZIP file and deploy the application.

### Option 2: Command Line (CLI)

Install the AWS CLI and Elastic Beanstalk CLI before beginning.

```bash
eb init
```
Initializes an Elastic Beanstalk application.

```bash
eb create my-environment-name
```
Creates an environment for the application.

```bash
eb deploy
```
Deploys application code to the environment.

### Additional Commands

| Command | Purpose |
|---|---|
| `eb open` | Opens the deployed application |
| `eb list` | Lists environments |
| `eb ssh` | Connects to an EC2 instance |
| `eb health` | Checks environment health |
| `eb terminate` | Terminates an environment |

## GitHub Actions and Auto-Deployment

GitHub Actions can automate deployment whenever changes are pushed to a configured branch.

This is part of **CI/CD (Continuous Integration and Continuous Deployment)**.

## AWS Billing and Safety

**AWS services can generate charges.**

Before deploying:

- Review AWS billing and pricing.
- Set up billing alerts.
- Monitor running services.
- Terminate unused environments after completing the lab.

## Code Challenges

### Code Challenge 16: Find Maximum Value

Find and return the maximum value stored in a binary tree.

### Code Challenge 17: Breadth-First Traversal

Traverse a binary tree level by level and return the values in the order visited.

## Key Takeaway

AWS provides cloud infrastructure for hosting applications. Elastic Beanstalk simplifies deploying Node.js servers, while EC2 provides the virtual computing resources.

Understanding deployment, scaling, and billing is important when managing cloud applications.

## Resources

- [AWS Documentation](https://docs.aws.amazon.com/)
- [AWS CLI Installation](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)
- [Elastic Beanstalk CLI Installation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) 