![[DNS Resolution.jpg]]

> [!info] DNS Resolution  
> DNS is the process that converts a human-readable hostname (like www.google.com) into an IP address that machines understand.

---
# 🌐 DNS Resolution - How IP Address is Obtained from Hostname

---

## 🟣 Overview

> [!info] DNS Concept  
> DNS (Domain Name System) is the process of converting a human-friendly hostname (e.g., `www.google.com`) into a machine-friendly IP address (e.g., `142.250.72.36`).

---

## ✅ DNS Resolution Workflow

### Step 1️⃣ Browser Cache

- [ ] Browser checks its internal **cache**.
    - ✅ If IP exists, directly use it.
    - ❌ If not, ask the **Operating System**.

---

### Step 2️⃣ Operating System (OS) Cache

- [ ] OS checks its own **DNS cache**.
    - ✅ If IP found, return it to the browser.
    - ❌ If not, contact the configured **DNS Resolver**.

---

### Step 3️⃣ DNS Resolver (Recursive Resolver)

- OS sends the DNS query to the **Resolver**.
    - Could be your ISP's resolver or a public one like `8.8.8.8` (Google Public DNS).
    - If resolver has cached entry, it returns the IP immediately.
    - If not, it performs a **full resolution**.

---

### Step 4️⃣ Root DNS Server

- Resolver queries the **Root DNS Server**.
    - Root does **NOT** give the IP.
    - Instead, it returns the address of the appropriate **TLD Server** (e.g., `.com` server).

---

### Step 5️⃣ TLD DNS Server

- Resolver queries the **TLD (Top-Level Domain) DNS server**.
    - TLD server returns the address of the **Authoritative Name Server** responsible for the requested domain (e.g., `google.com`).

---

### Step 6️⃣ Authoritative DNS Server

- Resolver queries the **Authoritative Name Server**.
    - The authoritative server provides the final **IP Address** of the requested hostname.

---

### Step 7️⃣ Cache & Use

- ✅ The Resolver caches the result.
- ✅ The OS caches the result.
- ✅ The Browser caches the result.
- ✅ Browser uses the resolved IP to establish a **TCP connection**.

---

## 📈 Visual Flow (Mermaid Diagram)

## 🟣 DNS Resolution - Mermaid Flowchart with Conditions

```mermaid
graph TD

A[User enters www.google.com] --> B{Browser Cache Hit?}
B -- Yes --> Z[Use cached IP and open TCP connection]
B -- No --> C{OS Cache Hit?}
C -- Yes --> Z
C -- No --> D{DNS Resolver Cache Hit?}
D -- Yes --> Z
D -- No --> E[Query Root DNS Server]
E --> F[Get TLD DNS Server]
F --> G[Query TLD DNS Server]
G --> H[Get Authoritative DNS Server]
H --> I[Query Authoritative DNS Server]
I --> J[Get Actual IP Address]
J --> K[Return IP to DNS Resolver]
K --> L[Cache IP in DNS Resolver]
L --> M[Return IP to OS]
M --> N[Cache IP in OS]
N --> O[Return IP to Browser]
O --> P[Browser caches IP]
P --> Z

