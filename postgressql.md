<p align="center">
  <img src="https://github.com/user-attachments/assets/04bf87a3-feb4-4e8a-b99e-27353fae3cf2" alt="PostgreSQL Logo" width="500"/>
</p>

# **PostgreSQL Documentation**

| Author         | Created on     | Version         | Last updated by | Last edited on |
|----------------|----------------|-----------------|-----------------|----------------|
| Mohamed Tharik | 2025-04-21     |     Version 1         | Mohamed Tharik  | 2025-04-21     |

## Introduction

PostgreSQL is a robust open-source relational database management system. Within the OT-MICROSERVICES architecture, PostgreSQL is primarily used as the backend database for services such as `attendance-api`.

---

## Purposes

PostgreSQL is used in the OT-MICROSERVICES project for the following:

- Storing and managing **attendance records** in `attendance-api`.
- Managing **user and admin information** securely.
- Supporting **complex queries** and **JSON-based** responses for APIs.
- Providing **ACID-compliant** transaction support across microservices.

---

## Key Features

- ACID-compliant transactions.
- JSON and JSONB support (used in dynamic payloads).
- Strong indexing and query optimization (used in filtering and reporting attendance data).
- Role-based access control.
- Extensible with user-defined types and functions.
- Supports concurrent users with MVCC (Multi-Version Concurrency Control).

---

## Getting Started

### Pre-requisites

| License Type        | Description                                         | Commercial Use | Open Source |
|---------------------|-----------------------------------------------------|----------------|-------------|
| PostgreSQL License  | Free and open-source under the PostgreSQL License   | Yes         | Yes       |

---

### Software Overview

| Software   | Version |
|------------|---------|
| PostgreSQL | 15.3    |

---

### System Requirements

| Requirement         | Minimum            | Recommended        |
|---------------------|--------------------|--------------------|
| Processor/Instance  | 1 vCPU / t2.micro   | 2 vCPU / t3.medium |
| RAM                 | 2 GB               | 4 GB               |
| Disk Space          | 10 GB              | 20 GB              |
| Operating System    | Ubuntu 20.04+      | Ubuntu 22.04 LTS   |

---

### Important Ports

| Port | Description                       |
|------|-----------------------------------|
| 5432 | Default PostgreSQL connection port |

---

## Dependencies

### Run-time Dependencies

- `libpq`: PostgreSQL C API
- `openssl`: For secure SSL communication

### Build-time Dependencies

- `gcc`, `make`
- `readline`, `zlib`, `libssl-dev`

---

