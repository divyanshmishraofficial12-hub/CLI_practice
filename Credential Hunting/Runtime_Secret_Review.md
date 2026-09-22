# Runtime Secret Review - CTF Write-up

This write-up covers the walkthrough and solution for the **Runtime Secret Review** challenge under the **foundation / creds** category on [CLI-Games](https://www.cli-games.com/terminal).

---

## 🎯 Challenge Objective

A monitoring stack at `10.0.2.15` (`monitor-stack`) is undergoing a credential-exposure review. The `ops` account has one approved diagnostic read of the captured service environment. The objective is to verify the access boundary, identify the runtime credentials exposed by `/proc`, and compare the active admin value with the service configuration in `grafana.ini`.

---

## 🖥️ Target Details

* **Target IP:** `10.0.2.15`
* **Hostname:** `monitor-stack`
* **SSH Credentials:** `ops` / `opsmonitor`
* **Category:** Foundation / Creds

---

## 🛠️ Step-by-Step Walkthrough

<img width="1429" height="836" alt="image" src="https://github.com/user-attachments/assets/f4dc7eec-58cb-42ba-8a16-1fda74a98d43" />

