<img src="https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png" alt="Git Logo" width="350"/><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" width="350"/>

# **VCS Setup Installation Guide** 

| Created        | Last updated      | Version         | author| comment | Reviewer |
|----------------|----------------|-----------------|-----------------|----------------|-----|
|2025-04-16  | 2025-04-21   |     Version 1        |  Mohamed Tharik | Internal Revivew    |Priyanshu|

## Purpose

This document outlines the design principles, key features, and a working Proof of Concept (POC) for implementing a Version Control System (VCS) in a software development lifecycle. It also includes a detailed installation and setup guide to get your VCS up and running using tools like Git.

## Table of Contents

- [Introduction](#introduction)
- [VCS Design Overview](#vcs-design-overview)
  - [1. Architecture](#1-architecture)
  - [2. Data Structure](#2-data-structure)
  - [3. Branching Strategy](#3-branching-strategy)
  - [4. Workflow Design](#4-workflow-design)
- [Proof of Concept (POC)](#proof-of-concept-poc)
  - [Objective](#objective)
  - [Tools Used](#tools-used)
  - [Steps](#steps)
  - [Outcomes](#outcomes)
- [VCS Setup: Installation & Configuration](#vcs-setup-installation--configuration)
  - [Prerequisites](#prerequisites)
  - [1. Install Git](#1-install-git)
  - [2. Configure Git](#2-configure-git)
  - [3. Initialize and Clone Repository](#3-initialize-and-clone-repository)
  - [4. Authentication](#4-authentication)
  - [5. Basic Workflow](#5-basic-workflow)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)
- [Disaster Recovery](#disaster-recovery)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

## Introduction 

A Version Control System (VCS) is a critical tool that manages changes to source code over time. It allows teams to work collaboratively, track revisions, roll back changes, and maintain code integrity throughout the software development lifecycle.

## VCS Design Overview

### 1. Architecture

- **Client-Server Model**: Central server (e.g., GitHub/GitLab) with developers pushing/pulling code.
- **DVCS (Distributed)**: Every developer has the full repository (e.g., Git).
- **Centralized VCS**: Single central repo, less flexible (e.g., SVN).

### 2. Data Structure

- **Git (Snapshots)**: Stores the full state of files in each commit.
- **SVN (Deltas)**: Stores only changes between versions.
- **Commit Hashes**: SHA-1 hashes uniquely identify commits.
- **HEAD**: Pointer to the current branch/commit.

### 3. Branching Strategy

- `main` / `master`: Stable production-ready code.
- `develop`: Active development and integration.
- `feature/*`: Feature-specific development.
- `release/*`, `hotfix/*`: For releases and urgent fixes.

### 4. Workflow Design

- **Git Flow**: Structured; good for planned releases.
- **GitHub Flow**: Lightweight; great with CI/CD.
- **Trunk-Based**: Fast-paced development on `main` with feature flags.

## Proof of Concept (POC)

### **Objective**:
Show how a team can collaborate using Git, manage branches, and integrate with CI.

### **Tools Used**:

- **Git** for versioning
- **GitHub** for remote hosting
- **GitHub** Actions for automation

### **Steps**:
1. Initialize a Git repo:
`git init`
2. Create and push to GitHub:
`git remote add origin https://github.com/org/project.git`
3. Branch and feature development:
`git checkout -b feature/login-page`
4. Push and create PR on GitHub
5. Set up GitHub Actions to run tests on push
6. Merge to `main` via PR after approval

### **Outcomes**

- Full code history available
- Pull Request with CI validation
- Rollback possible via commit hashes

## VCS Setup: Installation & Configuration

### **Prerequisites**:
- OS: Ubuntu / Windows / macOS
- Git installed
- Internet connection for remote repository (GitHub/GitLab)

### 1. Install Git
#### **Ubuntu**:
```bash
sudo apt update
sudo apt install git -y
```
#### **macOS (Homebrew)**:
```bash
brew install git
```
#### **Windows**:
Download and install Git from the official website: [git-scm.com](https://git-scm.com)

### 2. Configure Git
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global core.editor "vim" # Optional
```
### 3. Initialize and Clone Repository
```
git init  # Create new local repo
git clone https://github.com/your-org/your-repo.git
```
### 4. Authentication

- Use SSH keys or Personal Access Tokens (PAT) for authentication.
- Generate SSH key: ssh-keygen -t ed25519
- Add key to GitHub/GitLab in account settings.

### 5. Basic Workflow
```bash
git add .
git commit -m "Initial commit"
git push origin main
```
## Best Practices 

- Write meaningful commit messages (<type>: <short summary>)
- Follow branching strategies (e.g., Git Flow)
- Use `.gitignore` to avoid tracking unwanted files
- Tag releases (`git tag -a v1.0`)
- Regularly pull latest changes before starting work
- Protect main branches with required PR reviews

## Troubleshooting

### Git Push/Pull Errors
- **Solution**: Ensure you have the correct remote URL using `git remote -v`.
- **Fix permission denied**: Set up SSH keys or check your GitHub token.
- **Merge conflicts**: Run `git pull --rebase` or resolve conflicts manually before committing.

### Branch Confusion
- Use `git branch -a` to list local and remote branches.
- Use `git checkout branch-name` to switch.
- Run `git status` often to avoid confusion on which branch you're working in.

### Untracked or Lost Changes
- Use `git stash` to temporarily store local changes.
- Recover deleted files with `git checkout HEAD -- filename`.

## Disaster Recovery

### Backup Repositories
- Clone remote repo regularly:  
  ```bash
  git clone --mirror https://github.com/org/project.git

## Conclusion

Version Control Systems like Git are essential for modern software development. They enable teams to collaborate efficiently, track every change, and maintain clean, structured workflows using branches. With tools like GitHub or GitLab, teams can integrate CI/CD pipelines, manage code reviews via pull requests, and ensure high code quality. Combined with regular backups and proper recovery strategies, a well-designed VCS setup enhances productivity, code safety, and long-term maintainability.

## Contact Information

| Name | Email address         |
|------|------------------------|
| Mohamed Tharik  | md.tharik.sanaatak@mygurukulam.co    |

## References

| Links                                                                                                                                                                                                                     | Descriptions                                                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|[Install Git - GitHub Guides](https://github.com/git-guides/install-git)                | Official GitHub guide for installing Git          |  
