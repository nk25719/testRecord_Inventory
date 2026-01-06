 # Krake_DB

## Overview

**Krake_DB** is a lightweight web application backed by a relational SQL database for tracking **hardware boards** and their **test records** during manufacturing, testing, and servicing.

The system provides **traceability**, **non-duplicative records**, and **persistent storage of test results**, replacing ad-hoc logs and spreadsheets.

---

## Purpose

Krake_DB is built to answer these core questions:

- What boards exist?
- What is the current status of each board?
- What tests were run on a board, and when?
- Did a board pass or fail specific tests?
- Can test history be retrieved or exported later?

This tool is intended for **internal use** in factory, lab, or service environments.

---

## Core Features

### Board Management
- Register boards using a **serial number** as the primary identifier
- Store metadata such as:
  - Hardware revision
  - PCB revision
  - Batch
  - Assembly information
  - Board status (e.g. IN_STOCK, IN_TEST, SHIPPED)

### Test Record Tracking
- Log multiple test runs per board
- Separate handling of:
  - Powered test results
  - Unpowered test results
- Store individual test steps with pass/fail outcomes
- Preserve historical test data

### Relational Database Design
- Normalized SQL schema with parent → child relationships
- Core tables include:
  - `boards`
  - `test_runs`
  - `test_details`
  - `powered_results`
  - `unpowered_results`
- Foreign key constraints to prevent orphaned records

### Web Interface
- HTML-based UI for:
  - Registering and searching boards
  - Viewing test records
  - Browsing board history
- Table-based layout for clarity
- Export functionality (CSV / Excel)

### Deployment
- Designed to run locally or on a Linux server
- Can be managed as a system service for continuous operation

---

 

## Typical Workflow

1. Register a board with a unique serial number  
2. Perform tests externally (manual or automated)  
3. Log test results into Krake_DB, GDT info  
4. Review board status and test history  
5. Export records for reporting or archiving
6. Export QR code and serial number for tracking. 
