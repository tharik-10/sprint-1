# **Employee-API Setup and run the App for POC**

| Created        | Last updated      | Version         | author|  Internal Reviewer | L0 | L1 | L2|
|----------------|----------------|-----------------|-----------------|-----|------|----|----|
| 2025-04-25  | 2025-04-25   |     Version 1         |  Mohamed Tharik |Pritam|Khushi|Mukul Joshi |Piyush Upadhyay|

## Introduction 
This document captures the rough steps taken to set up and run the Employee API as part of a POC (Proof of Concept). It ensures the API is functional and ready for demonstration, helps track the installation process, and serves as a foundation for writing the final, detailed documentation. It also provides transparency for reviewers and assists in reproducing the setup when needed.

## Table of Contents

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

**Data Flow Diagram:**
```text
Client 
   │
   ▼
employee-api (Go Application)
   │
   ▼
Redis Cache
   │
   ▼
ScyllaDB
```

