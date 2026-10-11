# Task 03: Local Reconnaissance and Attack Surface Map

## 1. Target Scope & Isolation Verification
* **Target Address:** `http://localhost:3000` (OWASP Juice Shop / Local Lab)
* **Target IP:** `127.0.0.1` / Local Host-Only Subnet
* **Scope Status:** Verified isolated local environment (No external systems scanned)

---

## 2. Sanitized Command Log & Enumeration
Below are the commands used for local service enumeration and HTTP header analysis:

```bash
# 1. Local Port & Service Scan (Nmap)
nmap -sV -sC -p 3000 127.0.0.1 -oN nmap_recon_log.txt

# 2. HTTP Header Inspection (cURL)
curl -I http://localhost:3000

# 3. Directory & Route Enumeration
gobuster dir -u http://localhost:3000 -w /usr/share/wordlists/dirb/common.txt
