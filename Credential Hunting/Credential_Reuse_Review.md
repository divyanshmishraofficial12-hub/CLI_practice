# Credential Reuse Review - CTF Write-up

This write-up covers the walkthrough and solution for the **Credential Reuse Review** challenge under the **foundation / creds** category on [CLI-Games](https://www.cli-games.com/terminal).

---

## 🎯 Challenge Objective

A multi-service host at `10.0.2.20` (`multi-svc`) is being reviewed after one administrative credential was exposed. Inventory the reachable services, use the assigned administrative account, and determine which credentials are reused, separately stored, or embedded in the application.

---

## 🖥️ Target Details

* **Target IP:** `10.0.2.20`
* **Hostname:** `multi-svc`
* **SSH Credentials:** `admin` / `Summer2026!`
* **Category:** Foundation / Creds

---

## 🛠️ Step-by-Step Walkthrough

