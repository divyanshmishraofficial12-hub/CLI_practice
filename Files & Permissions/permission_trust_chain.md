# Permission Audit — Trust Chain

A practical documentation writeup covering privilege escalation paths, non-standard SUID binary inspection, and insecure configuration references in Linux environments.

---

## 📋 Challenge Overview

During a routine security audit, a nightly vault sync process exhibited anomalous behavior following a deployment. This exercise demonstrates how to trace an insecure permission trust chain from a privileged entry point down to exposed system credentials.

---

## 🎯 Audit Objectives

| Objective | Target | Description |
| :--- | :--- | :--- |
| **Privileged Entry** | SUID Helper | Identify the full path of the non-standard root-owned SUID helper binary. |
| **Loaded Configuration** | Config Path | Trace the full path of the configuration file sourced by the helper. |
| **Trusted Hook** | `SYNC_HOOK` | Determine the full file path assigned to `SYNC_HOOK` within the loaded config. |
| **Writable Group** | Group Permissions | Identify which user group possesses write permissions over the executed hook. |
| **Exposed Secret** | `DB_PASSWORD` | Extract the database password exposed through the hook's environment file. |

---

## 🛠️ Investigation & Commands

### 1. Identify Privileged Entry Point
Locate non-standard root-owned binaries with the SUID bit set:
```bash
find / -perm -4000 -user root -type f 2>/dev/null
