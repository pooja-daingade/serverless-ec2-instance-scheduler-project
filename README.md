# Serverless EC2 Instance Scheduler using AWS Lambda

##  Project Overview

A serverless AWS solution that automates **EC2 instance start/stop operations** using scheduled triggers, tag-based targeting, and least-privilege IAM permissions.

##  Project Objective

Automate EC2 instance **start/stop** operations using:

* AWS Lambda
* Amazon EventBridge Scheduler
* AWS IAM
* EC2 Resource Tags

**Goal:** Cost Optimization & Automated Instance Management.

##  Architecture
![Serverless EC2 Instance Scheduler Architecture]<img width="1536" height="1024" alt="Serverless EC2 Scheduler Architecture" src="https://github.com/user-attachments/assets/0ec5f743-0d0e-45ee-b3ba-a1995a903879" />

Lambda uses an **IAM least-privilege role** to identify and manage only the EC2 instances tagged for automation.

##  AWS Services & Technologies

| Service / Technology             | Usage                               |
| -------------------------------- | ----------------------------------- |
| **Amazon EventBridge Scheduler** | Triggers the automation on schedule |
| **AWS Lambda**                   | Executes EC2 start/stop logic       |
| **Amazon EC2**                   | Target instances                    |
| **AWS IAM**                      | Least-privilege access control      |
| **Python / Boto3**               | Automation logic                    |
| **EC2 Resource Tags**            | Dynamic instance targeting          |

##  Tag-Based Targeting

Target EC2 instances are identified using:

```text
AutoSchedule=true
```

This allows the Lambda function to dynamically identify the instances that should be managed.

##  Lambda Operations

The Lambda function supports two actions:

```json
{
  "action": "start"
}
```

and

```json
{
  "action": "stop"
}
```

Based on the action received from the scheduler, Lambda starts or stops the tagged EC2 instances.

##  Security

The solution follows the **Principle of Least Privilege** by granting Lambda only the required EC2 permissions.

* `ec2:DescribeInstances`
* `ec2:StartInstances`
* `ec2:StopInstances`

Permissions are restricted to instances with the required resource tag.

##  Cost Optimization

Automatically stopping EC2 instances when they are not required helps reduce unnecessary compute usage and supports **AWS cost optimization**.

##  Project Structure


##  Project Outcome

Successfully implemented an **automated and cost-efficient EC2 instance scheduling solution** using AWS Lambda, EventBridge Scheduler, IAM, and EC2 resource tags, enabling efficient instance management and optimized resource utilization.

##  Author

**Pooja Daingade**
