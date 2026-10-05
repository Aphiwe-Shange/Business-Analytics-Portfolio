# Customer Churn Analysis - 

## Overview 
A two-page Power BI dashboard analyzing customer churn for a telecommunications provider. PAge 1 gives a company-wide overview; Page 2 is a diagnistic deep-dive answering the question the ovview raises but does not explain: **what actaully drives customers to leave?

## Business problem 
The business knows roughly a quarter of its customers churn, but not *why*, or *which customers are highest-risk*. Without that, retention spend gets applied broadly instead of where it would have the most impact. This project was built to answer three questions:
1. What is the overall scale of churn, and who is churning (retained vs. lost)?
2. Which specific factors — contract type, tenure, service type, payment method — actually predict churn, and how strongly?
3. Where should retention efforts be concentrated first?

## Data Source
IBM Telco Customer Churn dataset — customer-level detail including tenure, contract type, internet service, payment method, monthly charges, and churn status (Yes/No).

## Tools Used
- **Power BI Desktop** — data modeling, DAX, visualization
- **DAX** — calculated measures and columns, including a `REMOVEFILTERS`-based company-wide churn rate benchmark, and a tenure-bucketing column with a custom sort order

---

## Report 1: Company-Wide Churn Overview (Page 1)

**Headline numbers:** 7K total customers · 2K churned · 5K retained · **26.54% churn rate**

**Findings:**
- Churned customers average roughly **half the tenure** of retained customers — churn is concentrated early in the customer lifecycle, not spread evenly.
- Month-to-month contracts show visibly higher churn volume than one-year or two-year contracts.
- Fiber optic customers churn more than DSL customers.
- Electronic check payers churn more than the other three payment methods.

This page shows churn is real and substantial. It doesn't yet show which factors matter most, or in combination — that's what Page 2 was built to isolate.

---

## Report 2: What Drives Churn? (Page 2)

**Company-wide churn rate benchmark: 26.54%**

I rebuilt this page around **churn rate**, not raw churn counts — a count-based view (e.g. "Fiber optic has the most churned customers") conflates a category's popularity with its actual risk. Rate-normalizing every chart is what surfaces the real drivers below.

**By Contract type:**
| Contract | Churn Rate |
|---|---|
| Month-to-month | 42.71% |
| One year | 11.27% |
| Two year | 2.83% |

**By Tenure:**
| Tenure | Churn Rate |
|---|---|
| 0–12 months | 47.04% |
| 13–24 months | 28.71% |
| 25–48 months | 20.39% |
| 48+ months | 9.05% |

**By Internet Service:**
| Service | Churn Rate |
|---|---|
| Fiber optic | 41.89% |
| DSL | 18.96% |
| No internet | 7.40% |

**By Payment Method:**
| Method | Churn Rate |
|---|---|
| Electronic check | 45.29% |
| Mailed check | 19.11% |
| Bank transfer (automatic) | 16.71% |
| Credit card (automatic) | 15.24% |

**The compounding finding — the strongest result on the page:**
> A Contract × Payment Method matrix shows that **Month-to-month customers paying by Electronic check churn at 53.73%** — more than double the company-wide baseline, and higher than either factor alone would suggest. At the opposite end, **Two-year customers paying by Mailed check churn at just 0.79%** — effectively a non-issue. The two factors don't just add together, they compound.

**Bottom line:** Churn isn't evenly distributed or driven by one cause — it's heavily concentrated in a specific, identifiable segment: new, month-to-month, electronic-check-paying, fiber optic customers. That segment is small enough to target directly, not so broad that a blanket retention program is the only option.

---

## Recommendations

| # | Recommendation | Rationale | Priority |
|---|---|---|---|
| 1 | Build a targeted retention offer for month-to-month + electronic check customers | This segment churns at 53.73%, over 2x baseline — the single highest-leverage intervention point | High |
| 2 | Incentivize contract upgrades (month-to-month → one/two-year) at the point of sale or renewal | Churn drops from 42.71% to 2.83% across the contract tiers — the strongest single lever in the dataset | High |
| 3 | Front-load engagement/support in the first 12 months of tenure | 47.04% of churn risk sits in this window alone — early intervention has the largest addressable pool | High |
| 4 | Investigate Fiber optic service quality or pricing perception | Fiber churns more than double DSL's rate despite presumably being the premium product — worth understanding why | Medium |
| 5 | Nudge Electronic check payers toward automatic payment methods | Automatic methods (Bank transfer, Credit card) churn at roughly a third of Electronic check's rate | Medium |

---

## Skills Demonstrated
- Diagnosing and correcting a count-vs-rate measurement error before drawing conclusions from it
- DAX: filter-context control (`REMOVEFILTERS`), calculated columns with custom sort ordering (tenure buckets)
- Cross-tabulation analysis (matrix) to find compounding, not just individual, risk factors
- Translating a churn analysis into segment-specific, prioritized retention recommendations

## Next Steps
- Model churn risk as a score combining all four factors, not just viewing them independently
- Add Monthly Charges as a fifth dimension to see if price sensitivity compounds with the existing risk factors
- Track these segments over time to measure whether a retention intervention actually moves the rate
