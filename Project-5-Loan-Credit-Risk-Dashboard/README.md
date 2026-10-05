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
> | Profit margind
