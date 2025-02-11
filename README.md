<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launch a Kubernetes Cluster

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-eks1)

**Author:** Gilbert Emodi  
**Email:** zemodi99@gmail.com

---

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks1_e5f6g7h8)

---

## Introducing Today's Project!

In this project, I will deploy a Kubernetes cluster ising Amazon EKS. EKS is AWS' service for deploying Kubernetes in the cloud. I will also be using exploring "eksctl" and CloudFormation

### What is Amazon EKS?

Amazon EKS is AWS' cloud Kubernetes service, which means it simplifies managing and orchestration of Kubernetes clusters. I used it in today's project to create a Kubernetes cluster.

### One thing I didn't expect

One thing I didn't expect in this project was seeing how eksctl wasn't already installed on the EC2 instance, but using it was well worth it. It simplified resource creation in comparison to using just the AWS CLI commands.

### This project took me...

This project took almost 2 hours to complete. The part that took the longest was the setup (downloading eksctl, and waiting for it to fully create the cluster environment.

---

## What is Kubernetes?

Kubernetes is a tool for container orchestration. Companies and developers use Kubernetes to deploy and manage large scale containerized applications.

I used eksctl to create a Kubernetes cluster using the command line. The "eksctl create cluster" command line I ran defined the name of the cluster, its node group's name, and node size settings. I also defined the region and the EC2 instance type.

I initially ran into 2 errors while using eksctl. The first one was because of not having installed eksctl yet.
The second one was because the EC2 instance didn't have permission to our AWS account and services yet.

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks1_ff9bfc221)

---

## eksctl and CloudFormation

CloudFormation helped create my EKS cluster because "eksctl" uses CF under the hood when I run an "eksctl create" command. CF created VPC resources because creating the EKS cluster in my default VPC would cause compatibility and permission issues.

There was also a 2nd CloudFormation stack for the node group. The difference between a cluster and node group is that the cluster is the entire Kubernetes set up (including the control plane), while the node group is a group of EC2 instances inside.

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks1_w3e4r5t6)

---

## The EKS console

I had to create an IAM access entry in order to see the nodes in the new node group. An access entry is a mapping of AWS IAM policies to Kubernetes' access control system. I set it up by using the Access Entries page within the EKS management console

It took about 40 minutes to create my cluster. Since I'll create this cluster again in the next part of the project, I can speed up the process by using templates (ex. Terraform or CloudFormation) and installing dependencies ahead of time.

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks1_e5f6g7h8)

---

## EXTRA: Deleting nodes

---

---
