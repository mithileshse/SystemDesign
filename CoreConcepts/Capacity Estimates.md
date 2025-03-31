# 📑  Capacity Estimation Snippet

`#template #capacity #system-design #cheatsheet`

---

## Template: Capacity Estimation

### ✅ Basic Storage Units

| Notation | Value                                   | Number Name | Read as        |
| -------- | --------------------------------------- | ----------- | -------------- |
| 10^3     | 1,000 Bytes                             | Thousand    | Kilobyte (KB)  |
| 10^6     | 1,000,000 Bytes                         | Million     | Megabyte (MB)  |
| 10^9     | 1,000,000,000 Bytes                     | Billion     | Gigabyte (GB)  |
| 10^12    | 1,000,000,000,000 Bytes                 | Trillion    | Terabyte (TB)  |
| 10^15    | 1,000,000,000,000,000 Bytes             | Quadrillion | Petabyte (PB)  |
| 10^18    | 1,000,000,000,000,000,000 Bytes         | Quintillion | Exabyte (EB)   |
| 10^21    | 1,000,000,000,000,000,000,000 Bytes     | Sextillion  | Zettabyte (ZB) |
| 10^24    | 1,000,000,000,000,000,000,000,000 Bytes | Septillion  | Yottabyte (YB) |

| Notation | Value                       | Read as       |
| -------- | --------------------------- | ------------- |
| 10^3     | 1,000 Bytes                 | Kilobyte (KB) |
| 10^6     | 1,000,000 Bytes             | Megabyte (MB) |
| 10^9     | 1,000,000,000 Bytes         | Gigabyte (GB) |
| 10^12    | 1,000,000,000,000 Bytes     | Terabyte (TB) |
| 10^15    | 1,000,000,000,000,000 Bytes | Petabyte (PB) |

---

### ✅ Time Estimations


| Time Unit | Exact                   | Approximation    |
| --------- | ----------------------- | ---------------- |
| 1 Day     | 86,400 sec              | ~ 10^5 sec       |
| 1 Week    | 604,800 sec             | ~ 6 × 10^5 sec   |
| 1 Month   | 2,592,000 sec (30 days) | ~ 2.5 × 10^6 sec |
| 1 Year    | 31,536,000 sec          | ~ 3 × 10^7 sec   |

---

---

### ✅ Quick Patterns

- Storage = Users × Frequency × Size × Time
    
- Bandwidth = QPS × Data per Query
    
- Total Data / sec = Events/sec × Data per Event
    

---

### ✅ Estimation Examples

#### Storage Estimate


`Scenario: 10M creators uploading 2 videos/week of 5GB each for 50 weeks   = 10 * 10^6 * 2 * 50 * 5 * 10^9 bytes   = 5 * 10^16 bytes = 50 PB/year`

#### Bandwidth Estimate


`Scenario: 2000 QPS serving 5GB each   = 2 * 10^3 * 5 * 10^9 = 10 * 10^12 bytes/sec = 10 TB/sec`

---

### ✅ Cache Formulae

| Metric              | Formula                                   |
| ------------------- | ----------------------------------------- |
| Effective Bandwidth | QPS × (1 - Cache Hit Rate) × Payload Size |
| CDN Egress          | Total Bandwidth × (1 - Cache Hit Rate)    |
| Typical Cache Hit   | ~70%-95%                                  |

---

### ✅ Compression Factors

| Data Type         | Compression Factor |
| ----------------- | ------------------ |
| Images/Media      | 1.5x - 2x          |
| Text (Logs, JSON) | 5x - 10x           |

---

### ✅ Latency Table (Rule of Thumb)

|Event|Latency|
|---|---|
|Memory Access|~100 ns|
|SSD Random Read|~100 µs|
|Network (In DC)|~0.5 ms|
|Network (Across DC)|~10-100 ms|
|Disk Sequential Read|~1 ms|

---

### ✅ Storage Growth Checklist ✅

-  Account for replicas
    
-  Consider backup/retention
    
-  Factor in spikes/load growth
    
-  Check compression opportunities
    
-  Cache hot data wherever possible
    
-  Include logging/monitoring overhead
    
-  Plan for peak QPS and average QPS separately
    

---

### ✅ Advanced Notes

- For **multi-region** systems: Storage ≈ Storage × N regions
    
- For **CDN heavy** apps: Actual egress ≈ 5%-30% of total due to cache
    
- For **real-time systems**: Always check latency, bandwidth, and availability trade-offs
    
- For **cost estimation**: Also consider $/GB/month for storage and $/GB for egress