![[DNS Resolution.jpg]]

> [!info] DNS Resolution  
> DNS is the process that converts a human-readable hostname (like www.google.com) into an IP address that machines understand.

---

## ✅ Step-by-Step DNS Resolution Process

### Step 1️⃣ Browser Cache

- [ ] Does the **browser** have the IP in its cache?
    - ✅ Yes → Use it directly.
    - ❌ No → Ask OS.

---

### Step 2️⃣ Operating System (OS) Cache

- [ ] Does the **OS** cache have the IP?
    - ✅ Yes → Return IP to browser.
    - ❌ No → Ask the DNS Resolver.

---

### Step 3️⃣ DNS Resolver

- The OS asks the **DNS Resolver**.
    - Usually, this is your ISP's DNS or a public resolver like `8.8.8.8`.

---

### Step 4️⃣ Root DNS Server

- The **Resolver** queries the **Root DNS Server**.
    - It will NOT return the IP.
    - It will return the address of the **TLD DNS server** (for example `.com` DNS server).

---

### Step 5️⃣ TLD (Top Level Domain) Server

- Resolver queries the **TLD server**.
    - It responds with the **Authoritative DNS Server** address for the target domain (like `google.com`).

---

### Step 6️⃣ Authoritative DNS Server

- Resolver queries the **Authoritative DNS Server**.
    - It returns the final IP address, e.g., `142.250.72.36`.

---

### Step 7️⃣ Cache and Return

- ✅ The resolver caches this IP.
- ✅ The OS caches this IP.
- ✅ The browser now connects to the server using this IP via **TCP**.

---

## 🪄 Visual Flow

```mermaid
graph TD
A[Browser] --> B[OS]
B --> C[DNS Resolver]
C --> D[Root DNS Server]
D --> E[TLD DNS Server]
E --> F[Authoritative DNS Server]
F --> G[Returns IP to Resolver]
G --> H[OS & Browser Cache IP]
H --> I[Browser opens TCP connection]
