# Config Exposure Review - CTF Write-up

This write-up covers the walkthrough and solution for the **Config Exposure Review** challenge under the **foundation / creds** category on [CLI-Games](https://www.cli-games.com/terminal).

---

## 🎯 Challenge Objective

A web application server at `10.0.2.5` (`app-server-01`) is undergoing a secret-storage review. Use the provided SSH credentials to log in, search through the configuration files, and identify:
1. The production database password.
2. The Stripe API secret key.
3. A retired database password remaining in a backup configuration file.

---

## 🖥️ Target Details

* **Target IP:** `10.0.2.5`
* **Hostname:** `app-server-01`
* **SSH Credentials:** `webapp` / `deploy2026`
* **Category:** Foundation / Creds

---

## 🛠️ Step-by-Step Walkthrough

<img width="1436" height="840" alt="image" src="https://github.com/user-attachments/assets/0176cc4d-a5fb-416a-85b3-d5c6ea3b5942" />
<img width="1427" height="843" alt="image" src="https://github.com/user-attachments/assets/0e7eed77-10e4-447c-97be-06b6553cd4e3" />
<img width="1436" height="836" alt="image" src="https://github.com/user-attachments/assets/544ad8e3-f1ce-4971-b0e9-96bda7a28a29" />
<img width="1431" height="839" alt="image" src="https://github.com/user-attachments/assets/a2f8e6fb-979c-4e39-bd13-0f85aaa9cb78" />
