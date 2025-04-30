<p align="center">
<img src="https://github.com/user-attachments/assets/cab1a539-b45d-4e0d-b7c1-4e97c8891f0e"" alt="Image" width="400"/>
</p>

# **POC of PR (Pull Request)**
| Created        | Last updated      | Version         | author|  Internal Reviewer | L0 | L1 | L2|
|----------------|----------------|-----------------|-----------------|-----|------|----|----|
| 2025-04-28 | 2025-04-28   |     Version 1         |  Mohamed Tharik |Priyanshu|Khushi|Mukul Joshi |Piyush Upadhyay|

## Purpose
The purpose of this document is to present a Proof of Concept (POC) for implementing a Pull Request (PR) strategy to enhance team collaboration, code quality, and traceability in modern development workflows. It emphasizes the importance of managing PRs to support incremental changes and better parallel development, using Git platforms like GitHub or GitLab.

## Table of Contents 
- [Purpose](#purpose)
- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [What is PR ?](#what-is-pr-)
- [PR Rules and Best Practices](#pr-rules-and-best-practices)
- [Step-by-Step Process for Creating a Pull Request (PR)](#step-by-step-process-for-creating-a-pull-request-pr)
- [Workflow of PR](#workflow-of-pr)
- [Use Case](#use-case)
- [Troubleshooting](#troubleshooting)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Reference](#reference)

## Introduction 
To implement a PR (Pull Request) strategy as a Proof of Concept (POC) for better collaboration, enhanced code review, and streamlined quality assurance within a software development workflow using Git-based version control systems like GitHub or GitLab.

## What is PR ?
PR is a collaborative version control practice where developers create a secondary pull request (PR) on top of a primary PR before it is merged into the main branch.For more details about PR refer to this repository [link]()

## PR Rules and Best Practices
| Rule | Description |
|------|-------------|
| **Naming Convention** | Use `feature/original-name-enhancement` or `bugfix/original-branch-fix` |
| **PR Description** | Mention that it's a PR of PR and link to the parent PR |
| **Tag the Original Author** | Ensure the base PR author is tagged for visibility and review |
| **CI/CD Setup** | CI pipelines should also trigger for PR of PRs if supported |
| **Merge Strategy** | Only merge into the base PR branch after approval |
| **No Direct Merge to Main** | A PR of PR must not be merged to `develop` or `main` directly |
| **Squash Commits Optional** | Use squash commits to keep history clean, especially in nested PRs |
| **Reviews Required** | Follow the same review policies as base PRs (e.g., 1-2 approvals required) |

## Step-by-Step Process for Creating a Pull Request (PR)

### Step 1: Clone the Repository Locally
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```
### Step 2: Create a New Branch
```bash
git checkout -b <your-feature-branch>
```
### Step 3: Make Changes to the Code
Edit or add the necessary code.

### Step 4: Stage Your Changes
```bash
git add .
```
### Step 5: Commit Your Changes
```bash 
git commit -m "Description of your changes"
```
### Step 6: Push Your Changes to GitHub
```bash 
git push origin <your-feature-branch>
```
### Step 7: Open a Pull Request
- Go to your repository on GitHub.
- Click on the "Compare & pull request" button, or go to Pull Requests tab and click "New Pull Request".
- Choose the base branch (typically main or develop) and the compare branch (the branch you just pushed).
- Add a title and detailed description of your PR.
- Click "Create Pull Request".

### Step 8: Review and Update (if needed)
- Wait for the code review from your team.
- If requested, make any changes by following steps 4-7 (stage, commit, and push).
- The reviewer may request additional changes or approve it.

### Step 9: Merge the PR
Once the PR is approved:

- If you have permissions, merge the PR into the base branch.
- If you don’t have permissions, the repository maintainer will merge it.

## Workflow of PR 
<p align="center">
<img src="https://github.com/user-attachments/assets/e4109088-53ff-462c-aed3-69d3eb33f074" alt="Image" width="400"/>
</p>

![image](https://github.com/user-attachments/assets/7dabc8a8-44b5-4e48-bda5-2c0bcc5c28fd)

## Use Case
Let’s say Developer A is working on Feature-X and has raised a PR against develop branch.

- Developer B wants to build additional logic on top of A’s changes, but A’s PR is not merged yet.
- Developer B checks out A's PR branch and creates a new branch from it, then raises a PR against A’s branch, not develop.
- This is the PR of PR.
- Once reviewed, B’s changes get merged into A’s PR branch, which then gets merged to develop.

## Troubleshooting
| Issue | Cause | Solution |
|-------|-------|----------|
| **Merge Conflict** | Conflicting changes in base & feature branch | Rebase or merge latest main/dev, resolve conflicts, and push |
| **CI/CD Failure** | Tests, lint, or build errors | Check pipeline logs, fix issues locally, re-push |
| **Missing Approvals** | Reviewers haven’t approved | Ping reviewers, ensure correct reviewers are tagged |
| **Wrong Base Branch** | PR raised against wrong branch | Edit PR base or raise a new one |
| **Incomplete PR Description** | Missing context or steps | Add summary, what/why/how, and testing instructions |
| **Review Feedback Pending** | Requested changes not made | Fix code, push changes, and tag reviewers again |
| **Stale Branch** | Behind main/develop | Rebase or merge main into feature branch |
| **Large PR** | Hard to review | Split into smaller PRs if possible, add clear commit messages |

## Conclusion 
This document outlines a structured Pull Request (PR) strategy to enhance collaboration, enable parallel development, and improve code quality. By following best practices like PR on top of PR, teams can manage dependencies efficiently and streamline reviews for faster, scalable development.

## Contact Information
| Name | Email address         |
|------|------------------------|
| Mohamed Tharik  | md.tharik.sanaatak@mygurukulam.co    |

## Reference
| Link                                                                 | Description                                               |
|----------------------------------------------------------------------|-----------------------------------------------------------|
|[GitHub: Creating a Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)|Official GitHub documentation on how to create a pull request, including UI steps and tips for collaboration.|
