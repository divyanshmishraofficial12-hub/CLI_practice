# Group Boundary Review

A hands-on writeup and investigation covering Linux file permissions, group membership boundaries, and parent directory permission vulnerabilities.

---

## 📋 Scenario Overview

A critical payment processing worker halted after its active configuration changed. This exercise focuses on tracing the failure from the application runtime down to weak group permissions and writable parent directory boundaries.

---

## 🎯 Lab Objectives

| Objective | Description | Target / Field |
| :--- | :--- | :--- |
<img width="1157" height="687" alt="image" src="https://github.com/user-attachments/assets/97a14720-5878-4b2b-896c-772e9e2e8cc2" />

| **Active Configuration** | Identify the full configuration file path loaded by the failing worker. | File Path |
<img width="1151" height="670" alt="image" src="https://github.com/user-attachments/assets/05ce540e-1110-42dd-b3fd-8d51032bdde8" />

| **Controlling Group** | Find which group holds write permissions on the active configuration file. | Group Name |
| **Unexpected Member** | Identify the account present in that group but missing from the approved roster. | Username |
| **Writable Parent** | Locate the group-writable parent directory that permits replacing the target file. | Directory Path |

---

## 🛠️ Investigation & Commands

### 1. Identify Loaded Configuration
Inspect the application service status or process logs to determine the exact config file in use:
```bash
cat /var/log/<service-name>.log
# or inspect the systemd service unit
systemctl status <service-name>
