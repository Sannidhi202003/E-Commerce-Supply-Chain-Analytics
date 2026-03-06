# 🛒 E-Commerce Supply Chain Intelligence

End-to-end supply chain analytics for a beauty & personal care e-commerce brand.  
Covers Skincare, Haircare & Cosmetics across 100 SKUs, 5 suppliers, 3 carriers, and 5 Indian cities.

---

## 📁 Project Structure

```
Ecommerce_Supply_Chain_Changed/
├── data/
│   ├── product_supply_data.csv       # Renamed from supply_chain_data.csv
│   └── dashboard_data.json           # Pre-computed aggregations for dashboard
├── notebooks/
│   └── supply_chain_intelligence.ipynb   # Refactored from E-commerce_Sales_Analysis.ipynb
├── dashboard/
│   └── supply_chain_analytics.html   # Interactive warm-theme dashboard (no upload needed)
├── models/                           # Reserved for future ML models
├── src/                              # Standalone scripts
└── README.md
```

---

## 📊 What's Analysed

| Question | Method | Chart Type |
|---|---|---|
| Price vs Revenue relationship | OLS Trendline Scatter | Scatter + trend |
| Sales volume by category | Groupby + Donut | Donut chart |
| Revenue by shipping carrier | Groupby + Comparison | Grouped bar |
| Shipping cost by carrier | Groupby + Bar | Bar chart |
| Defect rate per category | Groupby + Error bars | Bar with std dev |
| Transport mode cost share | Groupby + Donut | Styled donut |
| Supplier performance | Bubble chart | Scatter bubble |
| Location revenue | City groupby | Horizontal bar |

---

## 🎨 Dashboard — `supply_chain_analytics.html`

Open directly in any browser — **loads data automatically** (no file upload needed).

**Theme:** Warm coral/emerald retail aesthetic — completely different from other project dashboards.

| Chart | Style |
|---|---|
| Revenue by Category | Donut |
| Units Sold by Category | Donut |
| Defect Rate | Horizontal gradient bar |
| Carrier Revenue vs Cost | Grouped comparison bar |
| Transport Mode Cost | **Polar radial bar** (unique) |
| Revenue by City | Colour-scaled horizontal bar |
| Supplier Performance | Bubble scatter |
| Inspection Results | Pie |
| SKU Revenue Distribution | Histogram |
| Key Insights | 6 insight cards with colour coding |

---

## 🔧 Changes Made from Original

| Original | Changed To | What Changed |
|---|---|---|
| `E-commerce_Sales_Analysis.ipynb` | `supply_chain_intelligence.ipynb` | Renamed variables (`df`→`supply_df`), added feature engineering, added 8 new charts, restructured into 10 sections, added grouped stats |
| `supply_chain_data.csv` | `product_supply_data.csv` | Renamed file |
| No dashboard existed | `supply_chain_analytics.html` | Brand new interactive dashboard with 10 charts + KPIs |

---

## ⚙️ Setup

```bash
pip install pandas numpy plotly
```

```bash
jupyter notebook notebooks/supply_chain_intelligence.ipynb
```

---

## 💡 Key Findings

- **Skincare** is the top category by both revenue (₹241,628) and units sold (20,731)
- **Haircare** has the highest defect rate (2.48%) — 9% above the average
- **Mumbai** is the top-revenue city location
- **Road** transport is the most used mode but **Rail** has marginally higher total cost
- **Carrier B** leads in revenue contribution among the three carriers
