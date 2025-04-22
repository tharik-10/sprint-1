<img src="https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png" alt="Git Logo" width="350"/><img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub Logo" width="350"/>

# **VCS Setup Installation Guide** 

| Created        | Last updated      | Version         | author| comment | Reviewer |
|----------------|----------------|-----------------|-----------------|----------------|-----|
|2025-04-16  | 2025-04-21   |     Version 1        |  Mohamed Tharik | Internal Revivew    |Priyanshu|

## Purpose

This document outlines the design principles, key features, and a working Proof of Concept (POC) for implementing a Version Control System (VCS) in a software development lifecycle. It also includes a detailed installation and setup guide to get your VCS up and running using tools like Git.

## Table of Contents

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
