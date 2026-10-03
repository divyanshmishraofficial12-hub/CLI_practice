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
<img width="1149" height="674" alt="image" src="https://github.com/user-attachments/assets/ea6bf5c3-40eb-47b4-8abf-974e49487149" />
<img width="777" height="216" alt="image" src="https://github.com/user-attachments/assets/b0263f61-4f94-479d-aeb1-4aedbb755def" />
<img width="1146" height="674" alt="image" src="https://github.com/user-attachments/assets/0548dbdb-159d-49df-a484-7f56eb331ef3" />

