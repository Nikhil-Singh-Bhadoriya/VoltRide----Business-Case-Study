# 📊 VoltRide Financial Analysis



## 🎯 Executive Summary

**Analysis of 2,500 ride requests across 4 Indian cities reveals critical revenue leakage:**

### Key Findings at a Glance

| 💰 **REVENUE LOSS** | 🚨 **ROOT CAUSE** | 🎯 **TOP PRIORITY** |
|:---:|:---:|:---:|
| **₹485K Lost** | **30% Cancellation Rate** | **Fix Driver Availability** |
| (30% of potential GMV) | 739 cancelled rides | (Causes 42% of losses) |


### What This Analysis Covers

🏙️ **4 Cities:** Bengaluru, Delhi, Hyderabad, Mumbai  
📊 **2,500 Ride Requests** analyzed end-to-end  
💡 **Insights:** GMV leakage, cancellation drivers, battery impact, charging congestion

📁 **Data Source:** `DecodeX_VoltRide_Dataset.xlsx`

---


## 🚀 Quick Start Guide

### Step 1: Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn openpyxl
```

### Step 2: Run the Analysis
1. Place `DecodeX_VoltRide_Dataset.xlsx` in the same folder as the notebook
2. Open the notebook in Jupyter or VS Code
3. Run all cells (Kernel → Restart & Run All)
4. View results directly in the notebook

✅ **Expected Output:** 11 tables + 11 visualizations (nothing saved to disk)

---



## 💰 Financial Performance Summary



### 📈 The Big Picture

```
TOTAL POTENTIAL REVENUE:    ₹1,618,841
REVENUE EARNED:             ₹1,134,213  ✅
REVENUE LOST:               ₹484,627    ❌ (30% leakage!)
```



### Ride Outcomes

### Ride Outcomes

| Status | Count | Percentage | GMV |
|--------|------:|:----------:|----:|
| ✅ **Completed** | 1,761 rides | **70.4%** | ₹1,134,213 |
| ❌ **Cancelled** | 739 rides | **29.6%** | ₹484,627 lost |
| **TOTAL** | **2,500** | **100%** | ₹1,618,841 |



### 💡 What Do These Numbers Mean?

✅ **Good News:** 7 out of 10 rides complete successfully  
❌ **Bad News:** Nearly ₹500K in revenue evaporates due to cancellations  
⚡ **Surge Impact:** ₹332K (29% of completed revenue) comes from surge pricing



### Per-Ride Economics

| Ride Type | Average Fare |
|-----------|-------------:|
| Completed rides | ₹644 |
| Cancelled rides | ₹656 |

💡 **Insight:** Higher-value rides are slightly more likely to cancel (potential premium rider frustration)

---



## 🏙️ City Performance Breakdown

### Which City Loses the Most Money?

| City | Total Requests | Cancel Rate | 💰 Revenue Lost |
|------|---------------:|:-----------:|----------------:|
| 🔴 **Hyderabad** | 599 | **31.4%** | **₹129,706** 🚨 |
| 🟠 **Bengaluru** | 631 | 30.0% | ₹123,627 |
| 🟡 **Mumbai** | 638 | 28.2% | ₹118,733 |
| 🟢 **Delhi** | 632 | 28.8% | ₹112,561 |


💡 **Key Finding:** Hyderabad is the weakest performer with highest cancellations (31.4%) and losses (₹129.7K)

---



## 🚫 Why Are Rides Cancelled? (Root Cause Analysis)



### Who Cancels the Most?

| Cancelled By | Rides Lost | Revenue Lost | % of Total Loss |
|--------------|:----------:|-------------:|:---------------:|
| 👤 **Rider** | 335 | ₹218,753 | **45%** |
| 🚗 **Driver** | 251 | ₹165,584 | 34% |
| 💻 **System** | 153 | ₹100,291 | 21% |



### 🚨 THE BIGGEST PROBLEM: No Drivers Available

```
305 Ride Requests  →  NO DRIVERS  →  100% Cancellation

Lost Revenue: ₹203,133 (42% of all losses!)
```

💡 **Critical Insight:** Nearly **half of all lost revenue** comes from a single issue: not enough drivers when customers need rides

---



## 🔋 Battery Level Crisis



### ⚠️ Low Battery = Guaranteed Failure

| Battery Level | Rides Requested | Cancellation Rate | Revenue Lost |
|---------------|:---------------:|:-----------------:|-------------:|
| 🔴 **Below 20%** | 129 | **100%** ❌ | ₹83,845 |
| 🟠 20-39% | 590 | 23.9% | ₹89,250 |
| 🟡 40-59% | 571 | 24.9% | ₹95,482 |
| 🟢 60-79% | 599 | 26.4% | ₹107,440 |
| ✅ 80%+ | 611 | 27.7% | ₹108,610 |


```
🚨 CRITICAL FINDING: ALL 129 rides with <20% battery got cancelled
```

💡 **What This Means:** Range anxiety or system restrictions prevent low-battery vehicles from accepting rides. This is costing ₹84K in revenue.

---



## ⚡ Surge Pricing: Does It Hurt Conversions?

### Short Answer: No

| | Rides | Completion Rate |
|---|------:|:---------------:|
| **With Surge** (73% of all rides) | 1,838 | 70.4% |
| **No Surge** (27% of all rides) | 662 | 70.5% |

✅ **Good News:** Surge pricing doesn't increase cancellations—both have ~70% success rate

💡 **Reminder:** Surge contributes ₹332K (29% of all completed revenue), so it's critical for profitability

---



## 🔌 Charging Station Bottlenecks

### Most Congested Zones

| City | Zone | Wait per Charger | Status |
|------|------|:----------------:|:------:|
| 🔴 Delhi | Zone 5 | **16 min** | Critical |
| 🔴 Bengaluru | Zone 8 | **15.5 min** | Critical |
| 🟠 Hyderabad | Zone 6 | 11.3 min | High |
| 🟠 Hyderabad | Zone 8 | 11 min | High |



💡 **Insight:** Delhi Zone 5 and Bengaluru Zone 8 need immediate infrastructure expansion (15-16 min average wait!)

---



## 💵 Platform Revenue (What VoltRide Actually Keeps)

### Commission Rate Scenarios

| Take Rate | Earned | Lost to Cancellations |
|:---------:|-------:|----------------------:|
| 20% | ₹226,843 | ₹96,925 |
| **25%** | **₹283,553** | **₹121,157** |
| 30% | ₹340,264 | ₹145,388 |



💡 **Example:** At 25% commission, VoltRide keeps ₹283K but loses another ₹121K to cancellations

---


## 📈 Charts & Visualizations

The notebook auto-generates **11 charts** to help you spot patterns:

| # | Chart | What It Shows |
|---|-------|---------------|
| 1 | GMV Bar Chart | Potential vs Earned vs Lost revenue |
| 2 | Outcome Pie Chart | 70% completed / 30% cancelled split |
| 3 | Surge Uplift | How much extra revenue surge brings |
| 4 | Surge Comparison | Does surge hurt conversion? (No) |
| 5 | Revenue Scenarios | Platform earnings at different commission rates |
| 6 | Hourly Trends | When do requests & cancellations peak? |
| 7 | Zone-Hour Heatmap | Where & when is revenue lost? |
| 8 | Supply vs Leakage | Driver availability impact |
| 9 | Fare Boxplot | Are cancelled rides more expensive? |
| 10 | Battery Impact | Low battery = high cancellations |
| 11 | Charging Congestion | Which zones need more chargers? |

---


## 🎯 ACTION PLAN: Fix These 5 Things First



### 🥇 Priority #1: ADD MORE DRIVERS (Impact: ₹203K)
**The Problem:** 305 ride requests failed due to no drivers available  
**The Loss:** ₹203K (42% of all lost revenue)  
**Action:** Increase driver supply during peak hours in high-demand zones



### 🥈 Priority #2: FIX LOW-BATTERY DISPATCH (Impact: ₹84K)
**The Problem:** 100% cancellation rate when battery < 20%  
**The Loss:** ₹84K from 129 failed rides  
**Action:** 
- Don't assign rides to vehicles below 20% battery
- Auto-route low-battery drivers to nearest charging station
- Implement "heading to charger" status



### 🥉 Priority #3: REDUCE RIDER CANCELLATIONS (Impact: ₹219K)
**The Problem:** Riders cancel 45% of all requests  
**The Loss:** ₹219K  
**Action:**
- Improve ETA accuracy
- Better driver tracking & communication
- Investigate common rider complaints


### 4️⃣ Priority #4: EXPAND CHARGING IN HOTSPOTS (Impact: Operational)
**The Problem:** Delhi Zone 5 & Bengaluru Zone 8 have 15+ min waits  
**Action:** Deploy fast chargers in these two zones immediately



### 5️⃣ Priority #5: FIX HYDERABAD OPERATIONS (Impact: ₹130K)
**The Problem:** Worst performing city (31.4% cancellations)  
**The Loss:** ₹130K (highest among all cities)  
**Action:** Deep dive into Hyderabad-specific challenges

---


