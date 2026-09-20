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
<img width="1147" height="678" alt="image" src="https://github.com/user-attachments/assets/25976226-4a3b-412e-8d02-792bc153ce46" />

| **Unexpected Member** | Identify the account present in that group but missing from the approved roster. | Username |
<img width="1148" height="670" alt="image" src="https://github.com/user-attachments/assets/4c05a5d7-2815-48a9-a3e9-4d8fa5c86b6a" />

| **Writable Parent** | Locate the group-writable parent directory that permits replacing the target file. | Directory Path |
<img width="1146" height="681" alt="image" src="https://github.com/user-attachments/assets/174c8c95-55aa-499f-9789-a1c1309addfb" />

---

## 🛠️ Investigation & Commands

### 1. Identify Loaded Configuration
Inspect the application service status or process logs to determine the exact config file in use:
```bash
cat /var/log/<service-name>.log
# or inspect the systemd service unit
systemctl status <service-name>
