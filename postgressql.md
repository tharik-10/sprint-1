<p align="center">
  <img src="https://github.com/user-attachments/assets/04bf87a3-feb4-4e8a-b99e-27353fae3cf2" alt="PostgreSQL Logo" width="500"/>
</p>

# **PostgreSQL Documentation**

| Author         | Created on     | Version         | Last updated by | Last edited on |
|----------------|----------------|-----------------|-----------------|----------------|
| Mohamed Tharik | 2025-04-21     |     Version 1         | Mohamed Tharik  | 2025-04-21     |

## Introduction

This document provides a concise reference for understanding and using PostgreSQL within the OT-MICROSERVICES architecture. It explains its purpose, core features, setup requirements, and dependencies—specifically focusing on its role in services like attendance-api. It is intended for developers, DevOps engineers, and system administrators working on microservices that require relational data storage.

## What is PostgreSQL ?

**PostgreSQL** (often abbreviated as **Postgres**) is a powerful, open-source object-relational database system. It is known for its reliability, feature robustness, and standards compliance. Originally developed at the University of California, Berkeley, PostgreSQL has over 30 years of active development and a proven architecture.

## Why Use PostgreSQL ?

- Open Source & Free: No licensing fees, strong community support.
- Advanced Features: Supports complex queries, JSON, indexing (GIN, GiST, BRIN), and ACID compliance.
- Extensible: Custom data types, operators, and powerful extensions like PostGIS.
- Secure & Stable: SSL, advanced authentication, and strong data integrity.
- Scalable: Handles large datasets and high concurrency with ease.
- Cross-Platform: Compatible with Linux, Windows, macOS, and more.

## Key Features

- ACID-compliant transactions.
- JSON and JSONB support (used in dynamic payloads).
- Strong indexing and query optimization (used in filtering and reporting attendance data).
- Role-based access control.
- Extensible with user-defined types and functions.
- Supports concurrent users with MVCC (Multi-Version Concurrency Control).

## Getting Started

### Pre-requisites

| License Type        | Description                                         | Commercial Use | Open Source |
|---------------------|-----------------------------------------------------|----------------|-------------|
| PostgreSQL License  | Free and open-source under the PostgreSQL License   | Yes         | Yes       |

### Software Overview

| Software   | Version |
|------------|---------|
| PostgreSQL | 15.3    |

### System Requirements

| Requirement         | Minimum            | Recommended        |
|---------------------|--------------------|--------------------|
| Processor/Instance  | 1 vCPU / t2.micro   | 2 vCPU / t3.medium |
| RAM                 | 2 GB               | 4 GB               |
| Disk Space          | 10 GB              | 20 GB              |
| Operating System    | Ubuntu 20.04+      | Ubuntu 22.04 LTS   |

### Important Ports

| Port | Description                       |
|------|-----------------------------------|
| 5432 | Default PostgreSQL connection port |

## Dependencies

### Run-time Dependencies

- `libpq`: PostgreSQL C API
- `openssl`: For secure SSL communication

### Build-time Dependencies

- `gcc`, `make`
- `readline`, `zlib`, `libssl-dev`

## PostgreSQL Use Case in `attendance-api`

In the `OT-MICROSERVICES/attendance-api` project, PostgreSQL is used as the primary database to:

- Store employee attendance data (check-in, check-out, status).
- Enable API operations like creating, updating, and retrieving attendance records.
- Ensure reliable and structured storage using SQLAlchemy ORM.
- Support date/time queries and filtering for reports.

The connection is defined in `app.py`, and data models (like Attendance) are mapped to PostgreSQL tables in `models/attendance.py`.

## Conclusion 

PostgreSQL plays a critical role in the OT-MICROSERVICES/attendance-api by offering a reliable, secure, and feature-rich relational database solution. Its support for structured data, complex queries, and seamless integration with Python-based APIs ensures efficient management of attendance records. With PostgreSQL, the project benefits from open-source flexibility, high performance, and long-term scalability.

## Contact Information

| Name | Email address         |
|------|------------------------|
| Mohamed Tharik  | md.tharik.sanaatak@mygurukulam.co    |

## Reference 

| Links                                                                                                                                                                                                                     | Descriptions                                                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|

