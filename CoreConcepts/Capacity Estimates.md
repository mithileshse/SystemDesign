## 📒 Capacity Estimation Cheat Sheet (Back-of-the-Envelope)

---


## ✅ Basic Storage Units (Decimal System)

|Notation|Value in Bytes|Read as|
|---|---|---|
|10^3|1,000|Kilobyte (KB)|
|10^6|1,000,000|Megabyte (MB)|
|10^9|1,000,000,000|Gigabyte (GB)|
|10^12|1,000,000,000,000|Terabyte (TB)|
|10^15|1,000,000,000,000,000|Petabyte (PB)|

---

### ✅ **Time Approximations**

|Time Unit|Approximation|Rounded Estimate|
|---|---|---|
|1 day|24×3600=86,40024 \times 3600 = 86,40024×3600=86,400 sec|≈ 10510^5105 sec|
|1 week|7×1057 \times 10^57×105 sec|≈ 10610^6106 sec|
|1 month|30×10530 \times 10^530×105 sec|≈ 2.5×1062.5 \times 10^62.5×106 sec|
|1 year|365×105365 \times 10^5365×105 sec|≈ 3×1073 \times 10^73×107 sec|

---

### ✅ **Storage Capacity Estimation Example**

#### Scenario:

10 Million Creators upload 2 videos per week, each video is 5GB.

**Estimation:**

107 creators×2 uploads/week×4 weeks×12 months×5GB10^7 \text{ creators} \times 2 \text{ uploads/week} \times 4 \text{ weeks} \times 12 \text{ months} \times 5GB107 creators×2 uploads/week×4 weeks×12 months×5GB =10×106×100×5×109=1015×5=5×1015=5000PB/year= 10 \times 10^6 \times 100 \times 5 \times 10^9 = 10^{15} \times 5 = 5 \times 10^{15} = 5000 PB / year=10×106×100×5×109=1015×5=5×1015=5000PB/year

---

### ✅ **Server Bandwidth Estimation Example**

#### Scenario:

2000 QPS (Queries Per Second), each query transfers 5GB.

**Estimation:**

2000×5GB=2×103×5×109=10×1012 bytes/sec=10TB/sec2000 \times 5GB = 2 \times 10^3 \times 5 \times 10^9 = 10 \times 10^{12} \text{ bytes/sec} = 10 TB/sec2000×5GB=2×103×5×109=10×1012 bytes/sec=10TB/sec

---

### ✅ **Day to Seconds Quick Estimate**

|Exact|Approximation|
|---|---|
|1 Day = 86,400 sec|≈ 10510^5105 sec|
|1 Year = 31.5 million sec|≈ 3×1073 \times 10^73×107 sec|

---

### ✅ **Useful Approximations**

|Value|Approximation|
|---|---|
|24×360024 \times 360024×3600|≈ 100,000|
|25×400025 \times 400025×4000|= 100,000 (fast mental math)|
|1GB1GB1GB|10910^9109 bytes|
|1TB1TB1TB|101210^{12}1012 bytes|
|1PB1PB1PB|101510^{15}1015 bytes|

---

### ✅ **Quick Formula Patterns**

| Use-case              | Formula                         |
| --------------------- | ------------------------------- |
| Storage per Year      | Users × Frequency × Size × Time |
| Bandwidth             | QPS × Data per Query            |
| Total Data per Second | Events/sec × Data/Event         |