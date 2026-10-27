# Reading 16: AWS Cloud Servers (skipped for now due to paid service)

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

# CC16: Find Maximum Value in a Binary Tree

## Overview

The goal is to find the largest numeric value stored in a binary tree.

A **binary tree** is a data structure where each node can have up to two children: left and right.

## WHY — Why Is This Useful?

Finding the maximum value helps us understand how to traverse a tree, compare values, and process data stored in nodes.

## WHAT — What Is Required?

Create a method called `findMaximumValue()` for the Binary Tree class.

- **Arguments:** None
- **Returns:** Number
- **Goal:** Find the largest value in the tree.

## HOW — Algorithm Process

1. Start at the root node.
2. Set the initial maximum to the root's value.
3. Visit each node in the tree.
4. Compare the node's value to the current maximum.
5. Update the maximum if a larger value is found.
6. Return the maximum after checking all nodes.

## Example

```text
       10
      /  \
     5    20
    / \   /
   3   8 15
```

**Expected output:** `20`

## Approach and Efficiency

Using recursive depth-first traversal:

- **Time:** O(n) — Every node is visited once.
- **Space:** O(h) — Recursion uses space based on the tree's height.

## Key Concepts

- **Root:** The first node in a tree.
- **Node:** Stores a value and references to children.
- **Leaf:** A node without children.
- **Recursion:** A function calling itself to solve smaller parts of a problem.
- **Traversal:** Visiting nodes in a tree.

## Key Takeaway

Finding the maximum value requires examining every node because a regular binary tree does not guarantee that larger values are stored on a particular side.

- [AWS Documentation](https://docs.aws.amazon.com/)
- [AWS CLI Installation](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)
- [Elastic Beanstalk CLI Installation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) 