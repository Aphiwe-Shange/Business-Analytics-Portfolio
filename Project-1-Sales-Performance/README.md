# Sales Performance Dashboard - 

## Overview 
An interactive two page Power BI dashboard analyzing sales, profit, and regional performance for a retail business. PAge 1 gives a company-wide performance overview; Page 2 is a diagnostic deep-dive built specifically to answer a question the overview raises bust does not explain: **why is the South region underperforming?**

## Business Problem 
Leadership has visibility into top-line sales and progit numbers but no clear view of *where* performance is concentrated, *where* it is lagging, or *why*. Without that, budget and marketing decisions get made on gut feel rather tham evidence, This project was built to answer three qestions a business analyst would actually be asked:
1. Which regions and categories drive the most revenue and profit? 
2. Where is performance lagging, and what is the root cause - not just the symptom? 
3. What should the business prioritize next? 

## Data Source 
Sample Superstore dataset (retail sales data, 2014-2017) order-level detail including sales, profit, discount, category, sub-category, and customer segment.

## Tools Used
- ** Power BI Desktop** - data modelling, DAX, visualization
- **DAX** - calculated measures, including a region-aware Profit Margin % and a REMOVEFILTERS -based company-wide bechmark measure used to compare South against the who;e business on the same page

---

## Report 1: Company-Wide Performance Overview (Page 1) 

**Headline numbers:** R2.30M total sales - R286.40K total profit - 5k orders - 38K units sold - 12.47% profit margin

**Findings:**
-**West leads on both revenue and profit** - R108.42K profit (37.9% of total company profit), the highest of any region. 
-**South is the lowest-performing region** on both sales and profit, contributing only R46.75K (16.3%) of total profit. 
-**Technology is the most profitable category**. ahead of Office Supplies and well ahead of Furniture. 
-**Phones and Chairs are the top revenue-driving sub-categoryies** both carry outsized weight in overall sales. 
-**Sales grew steadily from 2014-2017**, with a dip through 2015 followed by a sharp acceleration into 2016-2017. 

This page tells what is happening. It does not yet explain why South lags which is what Page 2 was built to investigate.

---

## Report 2: Regional Deep-Dive - Why is the South Region Underperforming? (Page 2)

**South, isolated:** R391.72K sales - R46.75K profit - 822 orders - 6K units - **11.93% profit margin** 

**The key finding — and it's not what the initial data suggested:**

> South's profit margin (11.93%) is only 0.54 percentage points below the company-wide margin (12.47%). **South does not have a profitability problem — it has a revenue problem.** It's converting sales to profit at nearly the same efficiency as the rest of the business; it's simply generating less revenue overall (£391.72K vs. a ~£575K per-region average).

I went into this deep-dive expecting the cause to be over-discounting — the discount-vs-profit scatter was built specifically to test that. It doesn't hold up as the primary driver: most South transactions sit at low discount levels, and profit stays positive across nearly the full range. Profit only turns negative in one place:

- **Tables is the sole sub-category losing money in South** (negative profit bar in the Sub-Category chart) — every other sub-category is profitable, even the lowest-selling ones. This is a narrow, fixable problem, not a regional one.
- **Segment breakdown shows Consumer as the largest profit contributor in South**, followed by Corporate, then Home Office — the shortfall isn't concentrated in one customer segment, it's spread proportionally with sales volume.
- **South follows the same 2015 dip / 2016–2017 recovery trend as the company overall** — the region isn't declining in isolation, it's underperforming on a *level*, not a *trajectory*.

**Bottom line:** South needs a revenue-growth plan and a Tables-specific fix — not a company-wide discounting or margin intervention.

---

## Recommendations

| # | Recommendation | Rationale | Priority |
|---|---|---|---|
| 1 | Expand marketing and sales investment in the West region | Already leads on both revenue and profit — highest probability of return on further investment | High |
| 2 | Investigate why South generates lower sales volume (store count, staffing, local demand, marketing spend) | The deep-dive ruled out margin/discounting as the cause — the gap is in revenue generation, not efficiency | High |
| 3 | Review pricing, sourcing, or discontinuing Tables | The only sub-category losing money in South; fixing or dropping it directly improves regional profit | High |
| 4 | Continue prioritizing Technology products company-wide | Highest-profit category; deprioritizing would directly reduce overall profit | Medium |
| 5 | Prioritize inventory planning for Phones and Chairs | Highest-volume revenue drivers; stockouts here carry the largest revenue risk | High |

---

## Skills Demonstrated
- Business problem framing and hypothesis-driven analysis (testing and ruling out a discounting theory rather than assuming it)
- Power BI data modeling and DAX (including filter-context control with `REMOVEFILTERS` to build a same-page benchmark comparison)
- Multi-page dashboard design: overview + diagnostic drill-down
- Translating findings into prioritized, business-relevant recommendations

## Next Steps
- Quantify what's driving South's lower sales volume (needs data beyond this dataset — e.g. marketing spend or store count by region)
- Add a year-over-year growth measure to the trend page
- Apply this same overview-plus-diagnostic structure to a second, less commonly used dataset to demonstrate range
