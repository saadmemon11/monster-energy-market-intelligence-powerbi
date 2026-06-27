# 🟢 Monster Energy — Market Intelligence Dashboard
### Power BI | FMCG Analytics | India Energy Drinks Category | FY 2023

---

## 📌 Project Overview

This project simulates the kind of **retail market intelligence analysis** deliver to FMCG clients such as Monster Energy, PepsiCo, and Nestlé.

The dashboard tracks **Monster Energy's performance vs Red Bull** across India's energy drinks category — covering revenue, market share, variant performance, channel distribution, and regional insights — built entirely on a synthetic but realistic dataset modeled after real Indian FMCG retail data.

---

## 🎯 Business Context

> A brand like **Monster Energy** would use this dashboard to answer questions like:
> - How are we performing vs Red Bull across Modern Trade, Quick Commerce, and E-Commerce?
> - Which variant is growing fastest and in which region?
> - Where is our pricing positioned relative to the competition?
> - Which cities and channels represent untapped growth opportunities?

This is exactly the type of analysis provides to CPG/FMCG manufacturers on a weekly basis.

---

## 📊 Dashboard Pages

| Page | Description |
|---|---|
| **1. Overview** | KPI cards, monthly sales trend, market share donut |
| **2. Variant Analysis** | Revenue by variant, monthly trend by variant |
| **3. Channel & Region** | Channel performance, regional split, top cities table |
| **4. Competitor Intel** | Monster vs Red Bull head-to-head comparison |
| **5. Key Insights** | analyst observations and business conclusions |

---

## 🔢 Dataset Details

| Attribute | Details |
|---|---|
| Total Rows | 6,912 |
| Time Period | Jan 2023 – Dec 2023 (12 months) |
| Brands | Monster Energy, Red Bull |
| Monster Variants | Original, Ultra White, Mango Loco, Pipeline Punch, Rehab Tea, Zero Sugar |
| Red Bull Variants | Original, Sugar Free, Tropical |
| Regions | North India, South India, East India, West India |
| Cities | 16 cities (4 per region) |
| Channels | Modern Trade, Quick Commerce, E-Commerce, Kirana |
| Key Columns | Date, Brand, Variant, Region, City, Channel, MRP, Selling Price, Discount %, Units Sold, Revenue INR, Customer Satisfaction |

Dataset is synthetic and generated using Python for portfolio purposes.

---

## 📈 Key Findings

- **Monster Energy holds 66% revenue market share** vs Red Bull's 34% in India's energy drinks category
- **June 2023 was peak month** — 28,500+ units sold driven by summer seasonality (+34% surge)
- **Monster Original dominates** at 35% of all Monster variant sales
- **Quick Commerce contributes 28.4%** of Monster's revenue — overtaking Kirana (15.5%)
- **Mango Loco is the fastest-growing variant** — strongest performance in South and West India
- **Monster's average selling price (₹126)** commands a 15% premium over Red Bull (₹109)
- **Kirana channel is underpenetrated** — expansion opportunity in Tier-2 and Tier-3 cities

---

## 🛠️ Tools & Technologies

- **Power BI Desktop** — Dashboard design and visualization
- **DAX** — Custom measures for market share, MoM growth, revenue calculations
- **Python** — Synthetic dataset generation (NumPy, CSV)
- **Data Modeling** — Star schema with DateTable relationship

---


## 📐 DAX Measures Used

```dax
Total Revenue = SUM('Monster_Energy_Sales_Data'[Revenue_INR])

Monster Revenue = CALCULATE([Total Revenue], 'Monster_Energy_Sales_Data'[Brand] = "Monster Energy")

Market Share % = DIVIDE([Monster Revenue], [Total Revenue], 0) * 100

MoM Growth % = 
VAR CurrentMonth = [Monster Revenue]
VAR PrevMonth = CALCULATE([Monster Revenue], DATEADD(DateTable[Date], -1, MONTH))
RETURN DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0) * 100

Revenue in Crores = DIVIDE([Monster Revenue], 10000000)
```

---

## 📁 Files in This Repository

```
├── Monster_Energy_Dashboard.pbix       # Main Power BI file
├── Monster_Energy_Sales_Data.csv       # Dataset (6,912 rows)
├── Screenshots/
│   ├── Page1_Overview.png
│   ├── Page2_Variant_Analysis.png
│   ├── Page3_Channel_Region.png
│   ├── Page4_Competitor_Intel.png
│   └── Page5_Key_Insights.png
└── README.md
```

---

## 🚀 How to Use

1. Download **Monster_Energy_Sales_Data.csv** and **Monster_Energy_Dashboard.pbix**
2. Open the .pbix file in Power BI Desktop
3. If data doesn't load — go to **Home → Transform Data → Data Source Settings** and update the CSV file path to your local path
4. All visuals and measures will load automatically
