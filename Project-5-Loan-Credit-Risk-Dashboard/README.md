# Project 5 : Loan Portfolio Credit Risk & Profitability Dashboard 

An interactive Power BI dashboard that tells a lender's executives where their loan book makes money, where it loses money, and what to do about it. 

> **Data note:** The dataset is **synthetic** (12 000) artificially generated loans, fixed random seed, reproducible with `data/generate_dataset.py`). It is modelled on a South African consumer-lending book, in ZAR. No real customer data is used, and the findings describe this dataset, not any real, not any real bank.
>
> ---
>
> ## 1. The business challenge
>
> A customer lender has grwon its loan book quickly. The executive team asks three questions:
>
> 1. **Is the book actually profitable once credit losses, funding costs and acquisitions costs are included?**
> 2. **Which customer segments and products drive losses?**
> 3. **Which acquisition channels deliver profitable customers, not just volume?**
>
> ## 2. Data
> | File | [`data/loans.csv`](data/loans.csv) (12,000 loans, 22 columns) |
> | Period | Loans originated Jan 2024 - Jun 2026; snapshot 30 Sep 2026 |
> | Grain | One row per loan |
> | Dictionary | [`data/DATA_DICTIONARY.md`](data/DATA_DICTIONARY.md) |
>
> ## 3. Data model approach
>
> - One fact table (`loans`) plus a `Calendar` date table (relationship on `origination_date`)
> - Calculated columns for **Credit Band** and **DTI Band**
> - Measures for revenue, losses, costs, profit, margin, ROI, CAC and default rate
  ([`docs/dax-measures.md`](docs/dax-measures.md))
> - Three report pages: Executive Overview, Credit Risk Deep-Dive, Acquisition & Profitability
  ([`docs/build-guide.md`](docs/build-guide.md))

> ### KPI definitions
> | KPI | Definitions |
> |---|---|
> | Net profit | Interest income - credit losses - funding cost - acquisition cost |
> | Profit margin | Net Profit / interest income |
> | ROI | Net profit / total amount disbursed |
> | CAC | Acquisition cost / number of loans originated |
> | Default rate | Defaulted loans / all loans |
> | Loss ratio | Credit losses / interest income |
>
> ## 4. Headlone results
>
> | KPI | Value |
> |---|---|
> | Loans originated | 12 000 |
> | Total disbursed | R681.7M |
> | Interest income | R122.7M |
> | Credit losses | R410.M |
> | Funding cost | R45.9M |
> | Acquisition cost | R8.2M |
> | **Net profit** | **R27.6M** |
> | **Profit margin** | **22.5%** |
> | **ROI (on disbursed)** | **4.05%** |
> | **Average CAC** | **R682 per loan** |
> | Default rate | 9.9% |
> | Loss ratio | 33.4% |
>
> ## Key Insights
>
> ### 1. A small high-risk segment destroys value
> Customer with a credit score below 550 make up **14.3% of loans but 35.9% od all credit losses**, Their default rate is **27.5%**, compared with **1.7%** for scores of 740 and above. They are charged the highest rated (23.7% on average) yet still lose **R3.0** overall.
>
> ![Default rate by credit band](images/analysis_dafualt_by_credit_band.png)
>
> ### 2. The profit engine is the middle of the book
> The 620-679 band generates **R11.7M, about 42% of total net profit**. Addind the 680-739 band, the two bands deliver nearly three-qaurters of profit.
>
> ![Net profit by credit band](images/analysis_profit_by_credit_band.png)
>
> ### 3. Channel qaulity matters more than channel volume
> Existing customers earn **R3 496 net profit per loan** at a CAC of only **R150**. Brokers earn **R1 306 per loan (63% less)**, cost **R1 304 per loan acquire**, and have the highest default rate (11.8%).
>
> ![Channel profit and CAC](images/analysis_channel_profit_cac.png)
>
> ### 4. Vehicle finance carries the portfolio
> Vehicles finance is **22.7% of loans but 70.1% of net profit** (margin 28.4%). Personal loans are 50% of loans but only **11.1% of profit** (margin 12.0%)
>
> ### 5. Affordability and employment are early-warning signs
> Loans where debt-to-income exceeds 60% default at **19.3%** and lose money overall. Unemployed applicants default at **17.6%** with negative ROI (-1,1%).
>
> ### 6. A trap to avoid when reading the trend
> Default rated look lower for recent originated qaurters (for example 6.6% for Q2 2026 vs 13.8% for Q3 2024), **This is not evidence of improving credit quality.** Newer loans have had less tome to default. A fair comparison needsvintage analysis by months on book, so the dashboard should not present the tremd as an improvement.
>
> ### 6. Recommendations
>
> 1. **Tighten the credit policy for scores below 550 and DTI above 60%:** raise the cut-off, cap loan size or term, or require a guarantor, Excluding the sub-550 band in this dataset would lift margin from 22.5% to 29.4%,
> 2. **Shift acquisition mix** towards existing-customer cross-sell, referrals and digital, and renegotiate broker commission or require stricter broker credit criteria.
> 3. **Review personal-loan pricing:** margin is 12.2% against 28.4% for vehicle finance.
> 4. **Add vintage and roll-rate reporting** so management can judge new-ledding quality fairly.
>
> 5. *Limmitations: figures are from synthetic data, funding cost is estimated at a flat 7.5% on avarage balance, and "exclude a segment" scenarios ignore capital redevelopment and volume effects.*
>
> ## 7. Dashboard Preview
>
> ```
> images/Page1-Executive-Overview.png
> images/Page2-Credit-Risk-Deep-Dive.png
> images/Page3-Acquisition-Profitability.png
> ```

> ## 8. Repository structure

> ```
Project-5-Loan-Credit-Risk-Dashboard/
├── README.md
├── data/
│   ├── loans.csv
│   ├── generate_dataset.py
│   └── DATA_DICTIONARY.md
├── docs/
│   ├── dax-measures.md
│   └── build-guide.md
└── images/
```
> ## Skills Demonstrated
> 
> Financial KPI design (ROI, CAC, loss ratio), credit risk segmentation, data modelling (star schema, date table), DAX, dashboard design for executives, data storytelling and recommendations , awareeness of analytical pitfalls (data maturity bias).
