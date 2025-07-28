# ETLApp User Guide

Welcome to **ETLApp**, the all-in-one Extract, Transform, Load (ETL) desktop tool for Windows. This guide will help you install, configure, and use the application to move data from various sources to multiple destinations.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Launching the App](#launching-the-app)
4. [User Interface Overview](#user-interface-overview)
5. [Connection Management](#connection-management)

   * SQL Server
   * API Endpoint
   * CSV/Excel
   * Azure Blob Storage
   * SFTP
   * OneDrive
   * Anaplan
6. [Building and Running Jobs](#building-and-running-jobs)

   * Source Selection
   * Column Selection & Data Preview
   * Filters
   * Transformation & Profiling
   * Destination Selection
   * Job Naming & Scheduling
   * Running Now vs Scheduled
7. [Job Management](#job-management)

   * Save / Load Jobs
   * Secure Credential Storage
8. [Logging and Diagnostics](#logging-and-diagnostics)
9. [Advanced Features](#advanced-features)

   * AES Credential Encryption
   * Data Profiler
   * OneDrive Integration
   * Anaplan Import Trigger
10. [Troubleshooting & FAQ](#troubleshooting--faq)

---

## Introduction

ETLApp enables non-technical users to extract data from SQL Server, REST APIs, or flat files (CSV/Excel), perform basic transformations, and load the results into Azure Blob, SFTP, OneDrive, or Anaplan, with scheduling and logging built-in.

## Installation

1. **Download** the installer (`ETLAppInstaller.exe`) or the ZIP package.
2. **Run** the installer and follow the on-screen prompts to install to your chosen directory.
3. **Launch** the application via the Start Menu or desktop shortcut.

## Launching the App

* Double-click **ETLApp** in the Start Menu.
* On first launch, you’ll be prompted to enter a **master password** to unlock encrypted credentials (if enabled).

## User Interface Overview

* **Source Dropdown**: Switch between SQL Server, API, CSV, or Excel.
* **Connections Menu**: Manage all connection credentials in one place.
* **Dynamic Form Panel**: Displays fields for the selected source and preview table.
* **Destination Panel**: Configure export targets (Blob, SFTP, OneDrive, Anaplan).
* **Log Viewer**: Real-time activity log with open‑log button.
* **Scheduler Controls**: Set daily/weekly schedules.
* **Job Management**: Save & load job configurations.

## Connection Management

All credentials are stored securely (AES‑encrypted) and managed in the **Connections** menu.

### SQL Server

* **Server**: hostname or IP
* **Database**: target DB name
* **Username / Password**: SQL login
* **Test Connection** button

### API Endpoint

* **URL**: API base URL
* **Username / Password**: Basic Auth
* **Optional Headers**
* **Preview**: Fetch & display sample data

### CSV / Excel

* **Browse**: Select file path
* **Sheet (Excel only)**: Choose worksheet name
* **Preview**: Display first 100 rows

### Azure Blob Storage

* **Connection String**: Azure SAS or account key
* **Container**: target container name
* **Test Blob Upload** button

### SFTP

* **Host / Username / Password**
* **Remote Folder**: path on server
* **Test SFTP Upload** button

### OneDrive

* **Sign In**: OAuth popup
* **Folder Picker**: Browse OneDrive directory

### Anaplan

* **Workspace ID / Model ID**
* **File ID / Import Action ID**
* **Auth Token**
* **Upload & Trigger Import**

## Building and Running Jobs

1. **Select Source** via the dropdown.
2. **Configure Connection** fields displayed.
3. **Connect** or **Test** credentials.
4. **Select Table or Field List** (SQL/API/Flat). Use search to quickly find columns.
5. **Apply WHERE Clause** or filters.
6. **Preview Data** (Top 100 rows, sortable).
7. **Configure Destinations** (check boxes and enter credentials).
8. **Name Your Job**: Enter a descriptive job name.
9. **Run Now** with **Export** button, or set a **Schedule** (daily/weekly time).

## Job Management

* **Save Job**: Export configuration to encrypted JSON file.
* **Load Job**: Re-import configuration to reuse settings.
* Credentials remain encrypted; master password is used for decryption.

## Logging and Diagnostics

* **Activity Log**: Tracks exports, uploads, errors.
* **Open Log**: Button opens the rotating log file (`etl_app.log`).
* **Log Rotation**: 20 MB max file size with 3 backups.

## Advanced Features

### AES Credential Encryption

* Master password protects all saved credentials on disk.
* Credentials only decrypted in memory when needed.

### Data Profiler

* Column statistics: null count, unique values, min/max, mean/std.
* Quick insights into data quality and distribution.

### OneDrive Integration

* Uses OAuth2 to connect your Microsoft account.
* Choose a target folder for automatic CSV uploads.

### Anaplan Import Trigger

* After file upload, automatically start the configured import action.
* Monitor API response in the activity log.

## Troubleshooting & FAQ

**Q: I lost my master password.**
A: Credentials cannot be recovered—reset connections in the Connections menu.

**Q: Exports fail with timeout.**
A: Check network connectivity and credentials; use small preview before full export.

**Q: SFTP connection refused.**
A: Verify host, port (default 22), and firewall settings.

**Q: OneDrive OAuth window not appearing.**
A: Ensure pop-ups are allowed, or try running as administrator.

**Need more help?**
Contact your system administrator or consult the online documentation at \[YourCompanyDocsLink].
