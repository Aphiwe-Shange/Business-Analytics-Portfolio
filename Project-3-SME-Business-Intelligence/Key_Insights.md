# Key Insights — SME Business Intelligence Dashboard

## Executive Summary
Revenue grew 20% from 2017 to 2018 (600,193 to 722,052), driven broadly across the business but led disproportionately by two currently-smaller lines: Office Supplies (+32% by category) and Home Office (+51.3% by segment). Neither is the largest line in the business today, which means both represent genuine, underexploited growth opportunity rather than simply more of what's already dominant.

## 1. Data Quality Finding (addressed before analysis)
A date locale mismatch — source data in DD/MM/YYYY format being parsed as MM/DD/YYYY — caused 61% of total revenue to fall outside any valid year, invisible to every time-based chart, and silently mis-dated a further portion (e.g. 9 December read as September 12). This was identified via the Year slicer's blank bucket and confirmed against the Ship Date column, then corrected in Power Query by reapplying the date type conversion with the correct locale. All figures in this report reflect the corrected data, cross-validated across independent visuals (category totals vs. segment totals vs. regional trend totals) before being finalized.

## 2. Overall Growth
- 2017 revenue: 600,193
- 2018 revenue: 722,052
- **YoY growth: +20%**

## 3. Growth by Category
| Category | 2017 | 2018 | YoY Growth |
|---|---|---|---|
| Furniture | 195,813 | 212,314 | +8% |
| Office Supplies | 182,418 | 240,368 | +32% |
| Technology | 221,962 | 269,371 | +21% |

Office Supplies is the fastest-growing category despite being the smallest of the three by 2017 revenue.

## 4. Growth by Segment
| Segment | 2017 | 2018 | YoY Growth |
|---|---|---|---|
| Consumer | 291,143 | 328,604 | +12.9% |
| Corporate | 204,977 | 236,044 | +15.2% |
| Home Office | 104,073 | 157,404 | +51.3% |

Home Office — the smallest segment by revenue — is growing more than three times faster than Consumer, the largest segment.

## 5. What This Means
Growth is real and broad-based (every category and segment grew), but it is concentrated in the business's smaller lines rather than its largest ones. That's a favorable pattern: it suggests untapped demand in Office Supplies and Home Office rather than the business simply scaling its existing strengths, and it means there's runway before either catches up to the currently-larger lines.

## Recommendations

| # | Recommendation | Rationale | Priority |
|---|---|---|---|
| 1 | Increase investment in the Home Office segment | Fastest-growing segment (+51.3%) from the smallest base | High |
| 2 | Expand Office Supplies range and marketing | Fastest-growing category (+32%) | High |
| 3 | Investigate the driver behind Home Office and Office Supplies growth (new customers vs. existing customers buying more) | Determines whether to invest in acquisition or retention/upsell | Medium |
| 4 | Maintain, without over-indexing on, Technology and Consumer investment | Still largest and still growing, just more slowly than smaller lines | Medium |
| 5 | Audit remaining date fields for the same locale issue | The Order Date bug affected 61% of revenue before being caught | High |

## Methodology
Data source: SME sales dataset, 2015–2018. Analysis performed in Power BI. A date locale error was identified and corrected in Power Query before any year-based analysis was trusted. Key measures: Revenue 2017, Revenue 2018 (DAX, year-bound via `CALCULATE`), YoY Growth % (`DIVIDE` with a zero-fallback). Page 1: company-wide overview. Page 2: year-over-year growth broken out by category and by segment, cross-validated against a regional trend chart to confirm totals reconciled before reporting.
