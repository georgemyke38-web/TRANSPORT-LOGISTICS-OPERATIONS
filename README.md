# TRANSPORT-LOGISTICS-OPERATIONS
Transport &amp; Logistics operations analysis across 6 Texas hubs — 27,979 orders, 78.9% on-time delivery, 4.17/5 customer satisfaction. Includes Excel dashboard, Power BI visuals, and full project documentation
# Transport & Logistics Operations Performance Review

![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Orders](https://img.shields.io/badge/Orders-27%2C979-blue)
![OnTime](https://img.shields.io/badge/On--Time-78.9%25-orange)
![Satisfaction](https://img.shields.io/badge/Satisfaction-4.17%2F5-success)
![Hubs](https://img.shields.io/badge/Hubs-6-informational)
![Drivers](https://img.shields.io/badge/Drivers-55-yellow)

---

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Dataset Schema](#dataset-schema)
- [Key Performance Indicators](#key-performance-indicators)
- [Hub Network Analysis](#hub-network-analysis)
- [Vehicle Fleet](#vehicle-fleet)
- [Driver Performance](#driver-performance)
- [Delay Analysis](#delay-analysis)
- [Recommendations](#recommendations)
- [How to Contribute](#how-to-contribute)
- [Team](#team)

---

## Overview

This project analyses the operational performance of a **Transport & Logistics**
company operating a hub-and-spoke distribution model across **Texas**.
The analysis covers 27,979 orders across 6 hubs, 55 drivers, and 43 vehicles.

| Metric                    | Value          |
|---------------------------|----------------|
| Total Orders Processed    | 27,979         |
| On-Time Delivery Rate     | 78.9%          |
| Delay Rate                | 21.1%          |
| Cancelled Orders          | 252 (0.9%)     |
| Avg. Delivery Time        | 35.78 hours    |
| Avg. Hub Processing Time  | 1.97 hours     |
| Avg. Customer Satisfaction| 4.17 / 5       |
| Total Hubs                | 6 (Texas)      |
| Total Drivers             | 55             |
| Total Vehicles            | 43 (31 active) |

---

## Repository Structure

```
transport-logistics-analysis/
├── README.md
├── data/
│   └── project_dashboard.xlsx          # 27,979 order records (8 sheets)
├── presentation/
│   ├── Transport_Logistics_Presentation.pptx
│   └── Transport_Project_Layout.docx   # Slide blueprint
├── docs/
│   └── Transport_Logistics_Documentation.docx
└── assets/
    └── dashboard_screenshot.png        # Power BI / Excel dashboard
```

---

## Dataset Schema

### Orders (27,979 rows)

| Column                    | Type        | Description                        |
|---------------------------|-------------|------------------------------------|
| Order ID                  | Integer     | Unique order identifier            |
| Order Date                | Date        | Date order was placed              |
| Actual Delivery Date      | Date        | Date order was delivered           |
| Hub Name                  | String      | Processing hub location            |
| Driver ID / Driver Name   | Int/String  | Assigned driver                    |
| Vehicle Name / Type       | String      | Vehicle used for delivery          |
| Is Delayed / Is On Time   | Boolean     | Delivery status flags              |
| Delay Reason              | Categorical | Root cause of delay (10 categories)|
| Order Status              | Categorical | Delivered / Cancelled              |
| Delivery Time Hours       | Float       | Actual delivery duration           |
| Hub Processing Time Hours | Float       | Time spent at hub                  |
| Customer Satisfaction Score| Integer    | 1–5 scale                          |

### Vehicles (43 records)

| Column           | Description                          |
|------------------|--------------------------------------|
| Vehicle ID/Code  | Unique identifier (FT-001 format)    |
| Vehicle Model    | Mercedes Sprinter, Ford Transit etc. |
| Vehicle Status   | Active / Maintenance                 |
| Breakdown Count  | Number of breakdowns recorded        |
| Purchase Date    | Fleet acquisition date               |

### Drivers (55 records)

| Column              | Description                        |
|---------------------|------------------------------------|
| Driver ID/Name      | Unique identifier and name         |
| Employment Type     | Full-time / Part-time / Contract   |
| Hire Date           | Date of employment                 |
| Experience Years    | Years in role                      |
| Performance Rating  | 1–5 scale                          |

---

## Key Performance Indicators

```
┌────────────────────────────────────────────────────────────┐
│  KPI DASHBOARD SUMMARY                                     │
│────────────────────────────────────────────────────────────│
│  Total Orders              →  27,979                       │
│  On-Time Deliveries        →  22,071  (78.9%)              │
│  Delayed Deliveries        →   5,908  (21.1%)              │
│  Cancelled Orders          →     252  (0.9%)               │
│  Avg. Delivery Time        →  35.78 hours                  │
│  Avg. Hub Processing Time  →   1.97 hours                  │
│  Avg. Customer Satisfaction→   4.17 / 5                    │
│  Active Vehicles           →  31 of 43  (72%)              │
└────────────────────────────────────────────────────────────┘
```

---

## Hub Network Analysis

| Hub               | Capacity | Orders | On-Time % | Avg Sat. |
|-------------------|----------|--------|-----------|----------|
| Dallas Main Hub   | 250      | 7,345  | 78.9%     | 4.17     |
| Houston Hub       | 380      | 6,875  | 79.1%     | 4.17     |
| Austin Hub        | 220      | 4,065  | 77.9% ⚠  | 4.15     |
| San Antonio Hub   | 200      | 3,721  | 78.7%     | 4.16     |
| Fort Worth Hub    | 180      | 3,255  | 78.5%     | 4.17     |
| El Paso Hub       | 150      | 2,718  | 80.6% ✅  | 4.19     |

> ✅ **El Paso Hub** achieves the best on-time rate (80.57%) with the smallest
> capacity — use as the network benchmark.
> ⚠ **Austin Hub** has the lowest on-time rate and satisfaction — prioritise review.

---

## Vehicle Fleet

```
Fleet Status:
  Active (72%)      ███████████████████░░░░░░░  31 vehicles
  Maintenance (28%) ████████░░░░░░░░░░░░░░░░░░  12 vehicles

Orders by Vehicle Type:
  Van       (62.5%) ████████████████████████░░  17,480 orders
  Truck     (23.3%) █████████░░░░░░░░░░░░░░░░░   6,531 orders
  Pickup    (10.1%) ████░░░░░░░░░░░░░░░░░░░░░░   2,837 orders
  Box Truck  (4.0%) █░░░░░░░░░░░░░░░░░░░░░░░░░   1,131 orders
```

> ⚠ 28% of fleet in maintenance → directly causes 623 vehicle breakdown delays.
> Avg. 12.2 breakdowns/vehicle warrants an immediate preventive maintenance programme.

---

## Driver Performance

### Top Drivers by Order Volume

| Driver            | Orders | On-Time % | Avg Sat. |
|-------------------|--------|-----------|----------|
| Charles Thompson  | 1,531  | 78.8%     | 4.20     |
| Lisa Taylor       | 1,286  | 79.9% ✅  | 4.18     |
| Karen Rodriguez   | 1,233  | 77.8% ⚠   | 4.14     |
| Linda Taylor      | 1,202  | 78.4%     | 4.16     |
| Jennifer White    |   834  | 78.8%     | 4.18     |
| Donald Martin     |   804  | 78.9%     | 4.15     |
| David Davis       |   795  | 79.5%     | 4.16     |
| Elizabeth Harris  |   669  | 80.1%     | 4.17     |

### Performance Rating Distribution (55 Drivers)

| Rating     | Count | % of Team |
|------------|-------|-----------|
| 5 — Excellent | 6  | 10.9%     |
| 4 — Good      | 18 | 32.7%     |
| 3 — Average   | 22 | 40.0%     |
| 2 — Below Avg | 2  |  3.6%     |
| 1 — Poor      | 2  |  3.6%     |

---

## Delay Analysis

### Delay Reasons (5,908 total delayed orders)

| Delay Reason             | Count | % Delays | Controllable |
|--------------------------|-------|----------|--------------|
| Vehicle Breakdown        |  623  | 10.5%    | Yes ✅       |
| Road Construction        |  623  | 10.5%    | External     |
| Package Sorting Error    |  603  | 10.2%    | Yes ✅       |
| Driver Unavailable       |  595  | 10.1%    | Yes ✅       |
| Hub Processing Delay     |  589  |  9.9%    | Yes ✅       |
| Multiple Delivery Stops  |  586  |  9.9%    | Optimisable  |
| Severe Weather           |  585  |  9.9%    | External     |
| Customer Not Home        |  583  |  9.9%    | Partial      |
| Traffic Congestion       |  576  |  9.7%    | External     |
| Incorrect Address        |  545  |  9.2%    | Yes ✅       |

> Controllable delays (Vehicle Breakdown + Sorting Error + Driver Unavailable
> + Hub Processing + Incorrect Address) = **2,955 delays = 50% of all delays**.

---

## Recommendations

1. **Vehicle Maintenance Reform (Priority 1)**
   - Staggered maintenance schedule — max 10% of fleet at once (current: 28%)
   - Target fleet availability > 85%
   - Focus on Freightliner M2 and Ford F-150 (highest breakdown rates)

2. **Hub Process Standardisation (Priority 2)**
   - Audit and replicate El Paso Hub SOPs network-wide
   - Standardise package sorting to eliminate 603 sorting errors
   - Focus first on Austin Hub (lowest on-time rate: 77.9%)

3. **Driver Scheduling & Workforce Optimisation**
   - Review shift scheduling to address 595 Driver Unavailable delays
   - Convert high-performing part-timers to full-time
   - Structured coaching for 22 drivers rated 3/5

4. **Hub Capacity Rebalancing**
   - Redistribute volume from Dallas (over-strained) to Houston (under-utilised)
   - Evaluate long-term Dallas capacity expansion

5. **Technology & Route Optimisation**
   - Deploy route optimisation software (targets 586 multi-stop + 576 traffic delays)
   - Address verification at order entry (eliminates 545 incorrect address delays)
   - Customer delivery time slot notifications (reduces 583 not-home delays)

6. **Sustain Customer Satisfaction**
   - Protect 4.17/5 score through delay reduction
   - Use El Paso benchmark (4.19/5 + 80.57% on-time) as network target

---

## How to Contribute

1. Clone the repository
   ```bash
   git clone https://github.com/your-org/transport-logistics-analysis.git
   cd transport-logistics-analysis
   ```

2. Create a feature branch
   ```bash
   git checkout -b feature/your-update
   ```

3. Commit and push
   ```bash
   git add .
   git commit -m "docs: describe your change"
   git push origin feature/your-update
   ```

4. Open a Pull Request on GitHub

---

## Team

| Role             | Name                              |
|------------------|-----------------------------------|
| Team             | Sayo, Annie, George, Eniola       |
| Organisation     | .SAGE Inc.                        |
| Region           | Texas, USA                        |
| Dataset          | 27,979 orders · 8 Excel sheets    |
| Tools Used       | Excel, Power BI, PowerPoint       |

---
