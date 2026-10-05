# Key Insights — Superstore Sales Performance Dashboard

## Executive Summary
The business grew steadily from 2014–2017 with a sharp acceleration from 2016 onward, and is profitable overall at a 12.47% margin. Performance is concentrated: West drives the most revenue and profit, Technology is the most profitable category, and Phones/Chairs are the top revenue drivers. South is the lowest-performing region — but the deep-dive on Page 2 shows this is a **revenue gap, not a margin or discounting problem**, narrowed down to one specific loss-making sub-category (Tables).

## 1. Sales Performance
- **West** generated the highest sales revenue of any region; **South** recorded the lowest.
- Total company sales: **£2.30M**. South alone: **£391.72K** — roughly 32% below the ~£575K per-region average.

## 2. Profitability
- **West** also leads on profit: **£108.42K (37.9% of total company profit)**.
- Profit by region: West £108.42K (37.9%) · East £91.52K (32.0%) · South £46.75K (16.3%) · Central £39.71K (13.9%).
- **Technology** is the most profitable category, ahead of Office Supplies and Furniture.

## 3. Sales Trends
- Sales dipped through 2015, then grew sharply from 2016–2017.
- This trajectory supports continued investment in what's already working (West, Technology) rather than a defensive posture.

## 4. Product Performance
- **Phones** and **Chairs** are the top two revenue-driving sub-categories company-wide.
- Both are high-volume — any stockout or fulfillment issue with either carries outsized revenue risk.

## 5. Regional Deep-Dive: Why Is South Underperforming?
A dedicated dashboard page was built to test the most likely hypothesis — that South's profit is being eroded by heavy discounting.

**Finding: that hypothesis doesn't hold up.**
- South's Profit Margin: **11.93%**
- Company-wide Profit Margin: **12.47%**
- Gap: **0.54 percentage points** — small enough that discounting is not the primary driver.

**What actually explains the gap:**
- South's shortfall is almost entirely a **revenue volume** issue, not an efficiency issue — it converts sales to profit nearly as well as the rest of the company, it simply sells less.
- **Tables is the only sub-category losing money in South** — every other sub-category, even low-volume ones, is profitable. This is a narrow, addressable problem rather than a region-wide one.
- **Segment mix in South (Consumer > Corporate > Home Office)** roughly mirrors sales volume — the shortfall isn't concentrated in one customer segment.
- South follows the **same 2015 dip / 2016–2017 recovery trend** as the company overall — it's underperforming on level, not trajectory.

## Recommendations

| # | Recommendation | Rationale | Priority |
|---|---|---|---|
| 1 | Expand marketing and sales investment in the West region | Leads on both revenue and profit — highest probability of return | High |
| 2 | Investigate drivers of South's lower sales *volume* (store presence, staffing, local demand, marketing spend) | Deep-dive ruled out margin/discounting — the gap is in revenue generation, not efficiency | High |
| 3 | Review pricing, sourcing, or discontinuing Tables | Only sub-category losing money in South; a direct, fixable lever on regional profit | High |
| 4 | Continue prioritizing Technology products | Highest-profit category; deprioritizing would directly reduce overall profit | Medium |
| 5 | Prioritize inventory planning for Phones and Chairs | Highest-volume revenue drivers; stockouts carry the largest revenue risk | High |

## Methodology
Data source: Sample Superstore dataset (2014–2017). Analysis performed in Power BI using calculated DAX measures for Profit Margin %, Total Orders, and a `REMOVEFILTERS`-based company-wide margin benchmark that stays accurate even when the page is filtered to a single region. Page 1: company-wide KPI overview with regional, category, and sub-category breakdowns. Page 2: South-region diagnostic — profit by sub-category, profit by segment, and a discount-vs-profit scatter used to test (and rule out) a discounting-driven explanation.
