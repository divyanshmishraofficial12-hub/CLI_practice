# Permission Audit — Trust Chain

A practical documentation writeup covering privilege escalation paths, non-standard SUID binary inspection, and insecure configuration references in Linux environments.

---

## 📋 Challenge Overview

During a routine security audit, a nightly vault sync process exhibited anomalous behavior following a deployment. This exercise demonstrates how to trace an insecure permission trust chain from a privileged entry point down to exposed system credentials.

---

## 🎯 Audit Objectives

| Objective | Target | Description |
| :--- | :--- | :--- |
<img width="1149" height="680" alt="image" src="https://github.com/user-attachments/assets/22ea4f36-791c-49da-ae35-755c843e452b" />

| **Privileged Entry** | SUID Helper | Identify the full path of the non-standard root-owned SUID helper binary. |
| **Loaded Configuration** | Config Path | Trace the full path of the configuration file sourced by the helper. |
<img width="1150" height="675" alt="image" src="https://github.com/user-attachments/assets/28aeb816-6ef2-4610-8c86-83d97ac0c2b1" />
<img width="795" height="326" alt="image" src="https://github.com/user-attachments/assets/f46a3e7c-aaf4-47e6-87a1-0a9dbf969b36" />


| **Trusted Hook** | `SYNC_HOOK` | Determine the full file path assigned to `SYNC_HOOK` within the loaded config. |
| **Writable Group** | Group Permissions | Identify which user group possesses write permissions over the executed hook. |
| **Exposed Secret** | `DB_PASSWORD` | Extract the database password exposed through the hook's environment file. |
<img width="1153" height="665" alt="image" src="https://github.com/user-attachments/assets/09ad9c47-c189-425a-9919-4290b2c367f6" />

---



## 🛠️ Investigation & Commands

### 1. Identify Privileged Entry Point
Locate non-standard root-owned binaries with the SUID bit set:
```bash
find / -perm -4000 -user root -type f 2>/dev/null
