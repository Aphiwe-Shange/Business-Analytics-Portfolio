# Key Insights — Customer Churn Analysis Dashboard

## Executive Summary
Churn stands at 26.54% company-wide, but it is not evenly distributed. Four factors — contract type, tenure, internet service, and payment method — each independently predict churn, and they compound: the highest-risk segment (month-to-month contract + electronic check payment) churns at 53.73%, more than double the baseline, while the lowest-risk segment (two-year contract + mailed check) churns at just 0.79%.

## 1. Overall Churn
- Total customers: 7,000. Churned: ~2,000. Retained: ~5,000.
- Company-wide churn rate: **26.54%**.

## 2. Churn by Contract Type
| Contract | Churn Rate |
|---|---|
| Month-to-month | 42.71% |
| One year | 11.27% |
| Two year | 2.83% |

Contract length is the single strongest individual predictor in the dataset — churn drops by roughly 15x from month-to-month to two-year.

## 3. Churn by Tenure
| Tenure | Churn Rate |
|---|---|
| 0–12 months | 47.04% |
| 13–24 months | 28.71% |
| 25–48 months | 20.39% |
| 48+ months | 9.05% |

Nearly half of all customers in their first year churn. Risk falls steadily and substantially the longer a customer stays — the first 12 months is the critical retention window.

## 4. Churn by Internet Service
| Service | Churn Rate |
|---|---|
| Fiber optic | 41.89% |
| DSL | 18.96% |
| No internet | 7.40% |

Fiber optic — likely the premium-priced service — churns at more than double the rate of DSL, worth investigating on its own (pricing, competition, or service quality).

## 5. Churn by Payment Method
| Method | Churn Rate |
|---|---|
| Electronic check | 45.29% |
| Mailed check | 19.11% |
| Bank transfer (automatic) | 16.71% |
| Credit card (automatic) | 15.24% |

The two automatic payment methods churn at roughly a third of Electronic check's rate — payment friction (or the customer profile that chooses manual payment) is a meaningful churn signal on its own.

## 6. The Compounding Finding
A Contract × Payment Method matrix reveals that these factors don't act independently — they compound:
- **Month-to-month + Electronic check: 53.73% churn** — the single highest-risk segment identified.
- **Two-year + Mailed check: 0.79% churn** — effectively no churn risk.

This is the report's central finding: churn risk isn't a single dial, it's a combination. A customer with two "medium-risk" factors together can land in "severe-risk" territory.

## Recommendations

| # | Recommendation | Rationale | Priority |
|---|---|---|---|
| 1 | Build a targeted retention offer for month-to-month + electronic check customers | Highest-leverage single segment at 53.73% churn, over 2x baseline | High |
| 2 | Incentivize contract upgrades at point of sale or renewal | Churn falls from 42.71% to 2.83% across contract tiers — the strongest lever available | High |
| 3 | Front-load engagement and support in customers' first 12 months | 47.04% of this group churns — the largest single addressable risk pool | High |
| 4 | Investigate Fiber optic pricing or service quality | Over double DSL's churn rate despite being the premium offering | Medium |
| 5 | Encourage migration from Electronic check to automatic payment methods | Automatic payers churn at roughly a third of the Electronic check rate | Medium |

## Methodology
Data source: IBM Telco Customer Churn dataset. Analysis performed in Power BI. Key measures: Churn Rate % (using `REMOVEFILTERS` on the Churn column to maintain accuracy under page and visual-level filters), Total Customers (similarly filter-corrected), and a calculated Tenure Bucket column (0–12 / 13–24 / 25–48 / 48+ months) with a custom numeric sort order. Page 1: company-wide overview. Page 2: diagnostic breakdown by contract, tenure, internet service, and payment method, converted from raw counts to churn rate to avoid conflating category size with actual risk, plus a Contract × Payment Method matrix to surface compounding risk.
