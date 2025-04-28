![Go Logo](https://upload.wikimedia.org/wikipedia/commons/0/05/Go_Logo_Blue.svg)
# **Employee-API Setup and run the App for POC**

| Created        | Last updated      | Version         | author|  Internal Reviewer | L0 | L1 | L2|
|----------------|----------------|-----------------|-----------------|-----|------|----|----|
| 2025-04-25  | 2025-04-25   |     Version 1         |  Mohamed Tharik |Pritam|Khushi|Mukul Joshi |Piyush Upadhyay|

## Purpose 
This document captures the rough steps taken to set up and run the Employee API as part of a POC (Proof of Concept). It ensures the API is functional and ready for demonstration, helps track the installation process, and serves as a foundation for writing the final, detailed documentation. It also provides transparency for reviewers and assists in reproducing the setup when needed.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
  - [System Requirements](#system-requirements)
  - [Dependencies](#dependencies)
    - [Build Time Dependencies](#build-time-dependencies)
    - [Run Time Dependencies](#run-time-dependencies)
    - [Other Dependencies](#other-dependencies)
  - [Important Ports](#important-ports)
- [Architecture](#architecture)
  - [Data Flow Diagram](#data-flow-diagram)
- [Step-by-Step Installation](#step-by-step-installation)
- [Contact Information](#contact-information)
- [Reference](#reference)

## Introduction 
In [OT-Microservices](https://github.com/OT-MICROSERVICES/employee-api) , the Employee API is built on Golang which integrates with other APIs of the application.

## Prerequisites
Before deploying this application, ensure the following system and environment requirements are satisfied.
### System Requirements
|Hardware Specifications | Minimum Recommendation|
|----------------------|-------------------|
|Processor | Dual-core|
|RAM | 4 GB|
|Disk | 20 GB|
|OS | Ubuntu 22.04|

### Dependencies
**Build Time Dependencies**
|Name | Version | Description|
|-----|----------|-----------|
|Go | Latest| Golang compiler for building the application|
|Git | Latest | Version control system to clone the repository|
|Make | Latest | Build automation tool to manage build tasks|

**Run Time Dependencies**
|Name | Version | Description|
|------|----------|-------------|
|ScyllaDB | Latest | NoSQL database for storing employee data|
|Redis | Latest | In-memory data structure store for caching|

**Other Dependencies**
|Name | Version | Description|
|------|----------|-------------|
|Docker | Latest | Containerization platform to run services like ScyllaDB and Redis|

### Important Ports
|Port | Direction | Description|
|-------|----------|-------------|
|8080 | Outbound | Used by the Go application server|
|9042 | Inbound | Used by ScyllaDB|
|6379 | Inbound | Used by Redis|

## Architecture
The employee-api follows a microservices architecture with the following components:​

- **Client Layer**: Interfaces like browsers or API clients (e.g., Postman) that interact with the API.
- **API Layer**: The Golang-based RESTful service handling business logic.
- **Database Layer**: ScyllaDB serves as the primary data store, while Redis is used for caching to enhance performance.

### Data Flow Diagram:
<img src="https://github.com/user-attachments/assets/300e337d-0cc1-4c5a-9a21-e85f49ba1de2" width="300" />

## Step-by-Step Installation
### Step 1: Install Software Dependencies
```bash
sudo apt update
sudo apt install -y git golang make docker.io
```
### Step 2: Download the required Dependencies
```bash 
# Create Keyring Directory
sudo mkdir -p /etc/apt/keyrings

# Add ScyllaDB GPG Key
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys a43e06657bac99e3

# Add ScyllaDB Repository
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.2.list

# Update Package List and Install ScyllaDB
sudo apt update
sudo apt install scylla

# Run Scylla I/O Setup
sudo scylla_io_setup

# Start ScyllaDB Server
sudo systemctl start scylla-server

# Download the redis server for cache and Make for automate process
sudo apt install redis-server make 

# Download and Extract the Migrate package 
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz

# Move to System Binary Path for Migrate package 
sudo mv migrate /usr/local/bin/migrate
```
### Step 4: Configure ip address of ScyllaDB with our private ip 
```bash
cd /etc/scylla
sudo nano scylla.yaml
```
### Step 5: Create user and password for the ScyallaDB to store the data's 
```bash
# Login to the ScyllaDb and create user 
cqlsh
CREATE USER your_username WITH PASSWORD 'your_password';
# Keyspace is like database to store a data 
CREATE KEYSPACE employee_db WITH replication = {'class': 'SimpleStrategy', 'replication_factor' : 1};
```
### Step 6: Clone the Repository
```bash
git clone https://github.com/OT-MICROSERVICES/employee-api.git
cd employee-api
```
![Screenshot-134](https://github.com/user-attachments/assets/7f99d63e-316c-4e83-8a7d-8215f984c64f)

### Step 7: Configure ip addresses in the main files of the project 
```bash
sudo nano config.yaml
sudo nano migration.json
sudo nano main.go
```
### Step 8: Runs database migrations 
```bash
make run-migrations
```
### Step 9: Runs the unit test and generate code coverage report 
```bash
go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
go tool cover -html=cover.out
```
### Step 10: All configurations done we can run the application 
```bash
export GIN_MODE=release
# For debugging set gin mode to development
./employee-api
```
## Contact Information
| Name | Email address         |
|------|------------------------|
| Mohamed Tharik  | md.tharik.sanaatak@mygurukulam.co    |

## Reference
| Link                                                                 | Description                                               |
|----------------------------------------------------------------------|-----------------------------------------------------------|
| [Frontend Application](https://github.com/OT-MICROSERVICES/employee-api)                         | For setup and run the API refer to this Repository                  |
