# Geospatial-Analysis

# 📦 Warehouse Location Optimisation — Business Case

**Centre-of-Gravity (CoG) Model | Top 5 High-Delay Regions | E-commerce Logistics Analytics**

> A data-driven business case identifying the 5 highest-impact warehouse relocation opportunities to cut last-mile delivery delays and recover revenue lost to SLA breaches.

---

## 🎯 Business Problem

Last-mile delivery delays directly erode **customer lifetime value (CLTV)**, inflate **cost-to-serve**, and drag down **On-Time-In-Full (OTIF)** performance — three metrics that matter most to e-commerce operations and product teams.

This analysis pinpoints the 5 states with the worst delivery-delay rates in the dataset and quantifies the **fulfillment cost savings** achievable by relocating warehouse capacity closer to actual customer demand, rather than existing distribution infrastructure.

---

## 🧮 Methodology

### 1. Centre-of-Gravity (CoG) Model
Optimal warehouse coordinates are computed as the **demand-weighted centroid** of all delivery zip codes in a region:

```
Opt_Lat = Σ(demand_i × lat_i) / Σ(demand_i)
Opt_Lng = Σ(demand_i × lng_i) / Σ(demand_i)
```
where `demand_i` = order volume per zip code.

This minimizes aggregate transportation distance to the customer base — a standard OR/logistics-analytics technique adapted here for e-commerce fulfillment network design.

### 2. Cost-Saving Model
| Assumption | Value |
|---|---|
| Cost proxy | ₹50 per delayed order, per day of delay |
| National delay-rate benchmark (post-optimisation) | 8.4% |
| Projected delivery SLA | 11.0 days (median of "Good" delivery-zone tier) |
| Dataset duration | 23.4 months (Sep 2016 – Oct 2018) |

```
Monthly Saving = Prevented_Delayed_Orders/Month × ₹50 × Avg_Delay_Days
```

---

## 📊 Key Findings

| Rank | State | Current Avg Delivery | Projected Delivery | Delivery Reduction | Current Delay Rate | Annual Saving (₹) |
|---|---|---|---|---|---|---|
| 1 | Alagoas (AL) | 24.6 days | 11.0 days | **−55.2%** | 23.7% | ₹21,089 |
| 2 | Maranhão (MA) | 21.4 days | 11.0 days | **−48.6%** | 19.2% | ₹20,494 |
| 3 | Sergipe (SE) | 21.5 days | 11.0 days | **−48.9%** | 15.3% | ₹6,175 |
| 4 | Piauí (PI) | 19.4 days | 11.0 days | **−43.4%** | 15.2% | ₹6,958 |
| 5 | Ceará (CE) | 21.2 days | 11.0 days | **−48.2%** | 14.9% | ₹21,705 |

### 💰 Total Annual Saving — All 5 Warehouses Combined: **₹76,421**

**Headline insight for stakeholders:** Alagoas and Ceará alone contribute **~56% of total projected savings**, making them the priority sequencing for phase-1 warehouse rollout if capital is constrained.

---

## 📁 Repo Contents

| File | Description |
|---|---|
| `business_case_warehouse.xlsx` | Full model with 3 sheets: `Executive Summary`, `CoG Model Detail`, `Cost Saving Model` |

**Sheet breakdown:**
- **Executive Summary** — stakeholder-ready rollup: rankings, delivery reduction %, delay rates, monthly/annual savings per region
- **CoG Model Detail** — underlying demand-weighted coordinates, zip-code counts, and average delay-days per delayed order
- **Cost Saving Model** — assumptions, saving formula, and month-over-month prevented-delay math per region

---

## 🛠️ Tools & Techniques
- **Centre-of-Gravity (demand-weighted centroid) modeling** for network/facility-location optimization
- **Cost-proxy financial modeling** to translate operational KPIs (delay rate, delivery days) into ₹ business impact
- Built in Excel for direct stakeholder consumption; methodology is portable to Python (pandas/NumPy) or SQL for production-scale re-runs

---

## ⚠️ Assumptions & Limitations
- Cost proxy (₹50/delayed-order/day) is a simplifying assumption, not an audited logistics cost rate — treat savings as **directional, not exact**
- Model does not account for one-time warehouse setup/CapEx, only recurring delay-cost savings
- Based on a historical dataset (Sep 2016–Oct 2018); demand patterns and delay causes may have shifted

---

## 👤 Author

**Bhawna Kaushik** — Data Analyst
Team 4, with Sai Raja | PurpleMerit Internship Project

📫 [LinkedIn](https://linkedin.com) · [Portfolio](https://bhawna407.github.io/PORTFOLIO-WEBSITE) · [GitHub](https://github.com/bhawna407)
