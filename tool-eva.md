![image](https://github.com/user-attachments/assets/9af370df-1268-46bb-adc6-d48cb202ea1f)

# **Tool Evaluation of GitOps**

| Created        | Last updated      | Version         | author|  Internal Reviewer | L0 | L1 | L2|
|----------------|----------------|-----------------|-----------------|-----|------|----|----|
| 2025-04-28 | 2025-04-28   |     Version 1         |  Mohamed Tharik |Priyanshu|Khushi|Mukul Joshi |Piyush Upadhyay|

## Purpose
The purpose of this document is to evaluate and compare popular GitOps tools to help organizations automate and streamline their application deployment and infrastructure management. It provides a clear overview of the key tools available, compares their features, and assists teams in selecting the most suitable GitOps solution for their needs. The document aims to aid decision-making and improve the adoption of GitOps practices for efficient and automated continuous delivery.

## Table of Contents 

## Introduction 
- GitOps is a modern approach to managing and deploying applications and infrastructure using Git as the single source of truth.
- It leverages Git repositories to store declarative configuration files, enabling automated, consistent, and traceable deployments.
- With GitOps, all changes to infrastructure and application configurations are made through Git commits, ensuring that the desired state is always maintained across environments.
- This approach enhances operational efficiency by enabling continuous delivery, improving collaboration, and ensuring reliable and auditable deployments.

## What is GitOps ?
- GitOps is an operational framework that applies Git as the source of truth for managing infrastructure and application deployment processes. By storing all deployment specifications and configuration files in Git, teams can utilize Git’s built-in version control, branching, and auditing capabilities to manage cloud-native applications.
- GitOps enables continuous and automated delivery, reducing human intervention, and speeding up deployments.

## Why GitOps ?
| **Reason**                     | **Description**                                                                                       |
|---------------------------------|-------------------------------------------------------------------------------------------------------|
| **Automated Deployment**        | GitOps eliminates manual deployment steps and automates deployment pipelines using Git.                |
| **Consistency and Reproducibility** | Since all configurations are versioned in Git, deployments are reproducible, ensuring consistent environments. |
| **Auditability and Traceability** | Git provides a full audit trail of changes, ensuring that teams can trace issues back to specific commits. |
| **Reduced Complexity**          | GitOps simplifies the workflow by using familiar tools (e.g., Git, CI/CD) to manage deployments.        |
| **Improved Developer Experience** | Developers can use Git to manage infrastructure as code, improving collaboration and velocity.         |

## Different GitOps Tools

Here’s an overview of various GitOps tools available today:

### 1. **ArgoCD**     
<img src="https://github.com/user-attachments/assets/79fc2e0e-f689-4645-b2c4-0c60975591f4" width="200"/>

### 2. **Flux**      ![image](https://github.com/user-attachments/assets/55c2e707-0bba-4385-a260-2b5a744a59e0)

### 3. **Jenkins X**
![Jenkins X Logo](https://jenkins-x.io/images/jenkins-x-logo.png)

### 4. **Weaveworks GitOps**
![Weaveworks GitOps Logo](https://www.weave.works/images/logos/weaveworks-logo.svg)

### 5. **Rancher GitOps**
![Rancher GitOps Logo](https://rancher.com/docs/rancher/v2.5/en/gitops/assets/images/rancher-logo.svg)
