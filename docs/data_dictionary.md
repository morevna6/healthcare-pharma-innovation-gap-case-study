# Data Dictionary  
## Global Healthcare & Pharma Innovation Gap Case Study

This document describes the datasets used in the project, including their structure, key fields, and analytical role within the case study.

The project uses five main datasets:

1. `pharma_companies_financials.csv`
2. `drug_approvals.csv`
3. `clinical_trials.csv`
4. `biotech_funding.csv`
5. `disease_burden.csv`

The main analysis period is **2010–2025**. Records from 2026 were excluded from the main trend analysis because 2026 may represent an incomplete year.

---

## Dataset Source

The datasets used in this project come from the Kaggle dataset:

[Global Healthcare and Pharma 2010–2026](https://www.kaggle.com/datasets/sergionefedov/global-healthcare-and-pharma-2010-2026)

The dataset includes pharma company financials, drug approvals, clinical trials, biotech funding, and disease burden data. It combines public anchor sources with modeled or synthetic components, so the analysis should be interpreted as exploratory and portfolio-oriented.

---

# 1. pharma_companies_financials.csv

## Description

This dataset contains annual financial and operational metrics for major pharmaceutical and healthcare companies.

It is used to analyze:

- revenue growth
- R&D spending
- operating margins
- R&D intensity
- company-level innovation capacity
- segment-level differences

## Dimensions

| Column | Description |
|---|---|
| `year` | Reporting year. |
| `company_name` | Name of the pharmaceutical or healthcare company. |
| `ticker` | Stock market ticker symbol of the company. |
| `country_iso3` | ISO3 country code representing the company’s country. |
| `segment` | Company segment or business category, such as big pharma, biotech, diagnostics, generics, medical devices, or diversified pharma. |

## Measures

| Column | Description |
|---|---|
| `revenue_usd_bn` | Company revenue in billions of US dollars. |
| `operating_margin_pct` | Operating margin percentage. |
| `operating_income_usd_bn` | Operating income in billions of US dollars. |
| `rd_spend_usd_bn` | R&D spending in billions of US dollars. |
| `pipeline_size_est` | Estimated size of the company’s drug or product pipeline. |

## Derived KPIs

| KPI | Description |
|---|---|
| `rd_intensity_pct` | R&D spending as a percentage of revenue. |
| `total_revenue_usd_bn` | Total revenue over the analysis period. |
| `total_rd_spend_usd_bn` | Total R&D spending over the analysis period. |
| `avg_operating_margin_pct` | Average operating margin across the analysis period. |
| `avg_pipeline_size_est` | Average estimated pipeline size. |

## Analytical Role

This dataset supports the company performance layer of the case study. It helps answer which companies and segments had the strongest financial scale, R&D investment, and R&D intensity between 2010 and 2025.

---

# 2. drug_approvals.csv

## Description

This dataset contains drug approval records, including approval year, sponsor company, therapy area, drug type, and estimated commercial potential.

It is used to analyze:

- approval trends over time
- therapy area concentration
- sponsor company activity
- drug type distribution
- blockbuster and mega-blockbuster potential
- estimated commercial output

## Dimensions

| Column | Description |
|---|---|
| `approval_id` | Unique identifier for each drug approval record. |
| `approval_date` | Date of drug approval. |
| `year` | Approval year. |
| `drug_name` | Name of the approved drug. |
| `sponsor_company` | Company sponsoring or associated with the drug approval. |
| `drug_type` | Drug type, such as small molecule, biologic, vaccine, gene therapy, or cell therapy. |
| `therapy_area` | Therapeutic area associated with the drug approval. |
| `description` | Description or context of the approval. |
| `is_real_headline` | Indicator showing whether the record is based on a real headline or public reference point. |

## Measures / Flags

| Column | Description |
|---|---|
| `peak_sales_usd_bn_est` | Estimated peak sales potential in billions of US dollars. |
| `is_blockbuster` | Boolean flag indicating whether the drug is estimated to reach blockbuster status. |
| `is_mega_blockbuster` | Boolean flag indicating whether the drug is estimated to reach mega-blockbuster status. |

## Derived KPIs

| KPI | Description |
|---|---|
| `approval_count` | Number of drug approvals by company, year, or therapy area. |
| `blockbuster_count` | Number of approvals flagged as blockbusters. |
| `mega_blockbuster_count` | Number of approvals flagged as mega-blockbusters. |
| `estimated_commercial_output_usd_bn` | Total estimated peak sales potential by company or therapy area. |
| `avg_peak_sales_usd_bn` | Average estimated peak sales per approval. |

## Analytical Role

This dataset supports the innovation activity layer of the case study. It helps identify which therapy areas and companies received the most approval activity and estimated commercial output.

---

# 3. clinical_trials.csv

## Description

This dataset contains clinical trial records, including sponsor, therapy area, phase, enrollment, duration, outcome, and estimated stock impact.

It is used to analyze:

- clinical trial volume
- trial outcomes
- success and failure rates
- therapy area risk
- differences between Phase 2 and Phase 3 trials
- market reaction proxy through estimated stock impact

## Dimensions

| Column | Description |
|---|---|
| `trial_id` | Unique identifier for each clinical trial record. |
| `completion_date` | Date the trial was completed. |
| `year` | Completion year. |
| `sponsor` | Sponsor company or organization. |
| `therapy_area` | Therapeutic area associated with the trial. |
| `phase` | Clinical trial phase, mainly Phase 2 or Phase 3. |
| `outcome` | Trial outcome category, such as met primary endpoint, failed primary endpoint, or mixed results. |

## Measures / Flags

| Column | Description |
|---|---|
| `enrollment_n` | Number of participants enrolled in the trial. |
| `duration_months` | Trial duration in months. |
| `is_success` | Boolean flag indicating trial success. |
| `is_failure` | Boolean flag indicating trial failure. |
| `estimated_stock_impact_pct` | Estimated stock market impact percentage associated with the trial outcome. |

## Derived KPIs

| KPI | Description |
|---|---|
| `trial_count` | Number of trials by year, phase, or therapy area. |
| `successful_trials` | Number of successful trials. |
| `failed_trials` | Number of failed trials. |
| `trial_success_rate_pct` | Percentage of trials marked as successful. |
| `avg_stock_impact_pct` | Average estimated stock impact by outcome or therapy area. |

## Analytical Role

This dataset supports the clinical risk layer of the case study. It helps show that innovation activity should not be interpreted only through approval counts or commercial output, because clinical success rates vary significantly across therapy areas.

---

# 4. biotech_funding.csv

## Description

This dataset contains biotech funding and deal records, including deal type, investor or acquirer, target company, funding value, and megadeal flags.

It is used to analyze:

- biotech funding trends
- deal type distribution
- average deal size
- M&A versus VC dynamics
- megadeal concentration
- funding volatility over time

## Dimensions

| Column | Description |
|---|---|
| `deal_id` | Unique identifier for each funding or deal record. |
| `date` | Date of the deal or funding event. |
| `year` | Year of the deal or funding event. |
| `deal_type` | Type of deal, such as M&A, VC, IPO, licensing, partnership, or other funding category. |
| `acquirer_or_investors` | Acquirer, investor group, or funding source. |
| `target_or_company` | Target company or company receiving funding. |
| `description` | Description of the deal or funding event. |
| `is_real_headline` | Indicator showing whether the record is based on a real headline or public reference point. |

## Measures / Flags

| Column | Description |
|---|---|
| `value_usd_bn` | Deal or funding value in billions of US dollars. |
| `is_megadeal` | Boolean flag indicating whether the deal is considered a megadeal. |

## Derived KPIs

| KPI | Description |
|---|---|
| `total_funding_usd_bn` | Total funding value by year or deal type. |
| `deal_count` | Number of deals by year or deal type. |
| `avg_deal_size_usd_bn` | Average deal size in billions of US dollars. |
| `megadeal_count` | Number of megadeals. |
| `funding_share_pct` | Share of total funding represented by each category. |
| `deal_count_share_pct` | Share of total deal count represented by each category. |

## Analytical Role

This dataset supports the funding concentration layer of the case study. It helps show that biotech funding is highly concentrated and that megadeals can account for a large share of total funding value despite representing a small share of deal count.

## Important Note

Funding data was not directly included in the therapy-area innovation gap score because the available deal descriptions could not be reliably mapped to therapy areas. This limitation was documented rather than forcing an unreliable mapping. Humanity survives one more avoidable false precision event.

---

# 5. disease_burden.csv

## Description

This dataset contains disease burden estimates across years, regions, and diseases.

It is used to analyze:

- global disease burden trends
- regional disease burden concentration
- disease-level burden patterns
- burden-to-therapy-area mapping
- innovation gap analysis

## Dimensions

| Column | Description |
|---|---|
| `year` | Year of disease burden estimate. |
| `region` | Geographic region or country-level grouping. |
| `disease` | Disease or disease group. |

## Measures

| Column | Description |
|---|---|
| `dalys_millions` | Disease burden measured in millions of DALYs for the specific region and disease. |
| `global_dalys_millions` | Global disease burden measured in millions of DALYs for the disease. |

## Derived KPIs

| KPI | Description |
|---|---|
| `total_dalys_millions` | Total DALYs by region, disease, or therapy area. |
| `avg_dalys_millions` | Average DALYs by region, disease, or therapy area. |
| `avg_global_dalys_millions` | Average global DALYs by mapped therapy area. |
| `disease_burden_rank` | Rank of therapy area by disease burden. |

## Analytical Role

This dataset supports the health burden layer of the case study. It is used to compare pharmaceutical innovation activity with real-world disease burden across mapped therapy areas and regions.

---

# 6. Therapy Area Mapping

## Description

To compare disease burden with pharmaceutical innovation activity, disease groups were mapped to therapy areas.

This mapping was necessary because drug approvals and clinical trials were organized by therapy area, while disease burden data was organized by disease group.

## Example Mapping

| Disease Group | Mapped Therapy Area |
|---|---|
| Cancer | Oncology |
| Cardiovascular disease | Cardiovascular |
| Stroke | Cardiovascular |
| Neurological disorders | Neurology |
| Alzheimer's & dementias | Neurology |
| Mental disorders | Psychiatry |
| Diabetes | Metabolic |
| Chronic respiratory | Respiratory |
| Lower respiratory infections | Infectious |
| Tuberculosis | Infectious |
| Malaria | Infectious |
| HIV/AIDS | Infectious |
| COVID-19 | Infectious |
| Diarrheal diseases | Gastrointestinal |
| Liver disease | Gastrointestinal |
| Kidney disease | Gastrointestinal |
| Neonatal disorders | Rare disease |
| Maternal disorders | Rare disease |
| Self-harm | Psychiatry |

## Important Note

The mapping was created for analytical comparison and should be interpreted as an assumption-based framework. Some diseases may overlap multiple therapy areas, and some mappings may simplify more complex clinical realities.

---

# 7. Dashboard Export Files

The following CSV files were created from the analysis notebooks for Tableau dashboard development.

## yearly_trends_dashboard.csv

Used for the Executive Overview dashboard.

| Column | Description |
|---|---|
| `year` | Year of analysis. |
| `total_revenue_usd_bn` | Total pharma revenue in billions of US dollars. |
| `total_rd_spend_usd_bn` | Total R&D spending in billions of US dollars. |
| `rd_intensity_pct` | R&D spending as a percentage of revenue. |
| `approval_count` | Number of drug approvals. |
| `trial_count` | Number of clinical trials. |
| `total_funding_usd_bn` | Total biotech funding in billions of US dollars. |
| `total_dalys_millions` | Total disease burden in millions of DALYs. |

## company_kpis_dashboard.csv

Used for the Company Performance dashboard.

| Column | Description |
|---|---|
| `company_name` | Company name. |
| `segment` | Company segment. |
| `total_revenue_usd_bn` | Total revenue across the analysis period. |
| `total_rd_spend_usd_bn` | Total R&D spending across the analysis period. |
| `rd_intensity_pct` | R&D spending as a percentage of revenue. |
| `total_approvals` | Number of drug approvals associated with the company. |
| `blockbuster_count` | Number of blockbuster approvals. |
| `mega_blockbuster_count` | Number of mega-blockbuster approvals. |
| `estimated_commercial_output_usd_bn` | Estimated commercial output in billions of US dollars. |
| `approval_productivity_per_bn_rd` | Drug approvals per billion dollars of R&D spending. |
| `commercial_output_per_bn_rd` | Estimated commercial output per billion dollars of R&D spending. |
| `blockbuster_rate_pct` | Share of approvals estimated to be blockbusters. |

## therapy_area_innovation_gap_dashboard.csv

Used for the Innovation Gap dashboard.

| Column | Description |
|---|---|
| `therapy_area` | Therapy area. |
| `approval_count` | Number of drug approvals. |
| `estimated_commercial_output_usd_bn` | Estimated commercial output in billions of US dollars. |
| `avg_peak_sales_usd_bn` | Average estimated peak sales per approval. |
| `blockbuster_count` | Number of blockbuster approvals. |
| `mega_blockbuster_count` | Number of mega-blockbuster approvals. |
| `trial_count` | Number of clinical trials. |
| `successful_trials` | Number of successful clinical trials. |
| `failed_trials` | Number of failed clinical trials. |
| `trial_success_rate_pct` | Clinical trial success rate percentage. |
| `avg_stock_impact_pct` | Average estimated stock impact. |
| `avg_global_dalys_millions` | Average global disease burden in millions of DALYs. |
| `disease_burden_rank` | Rank by disease burden. |
| `approval_rank` | Rank by approval count. |
| `commercial_output_rank` | Rank by estimated commercial output. |
| `trial_activity_rank` | Rank by clinical trial activity. |
| `innovation_rank` | Combined innovation activity rank. |
| `innovation_gap_score` | Difference between innovation rank and disease burden rank. |

## funding_deal_type_dashboard.csv

Used for the Funding & Burden dashboard.

| Column | Description |
|---|---|
| `deal_type` | Type of biotech funding or deal. |
| `total_funding_usd_bn` | Total funding value in billions of US dollars. |
| `deal_count` | Number of deals. |
| `avg_deal_size_usd_bn` | Average deal size in billions of US dollars. |
| `megadeal_count` | Number of megadeals. |

## megadeal_summary_dashboard.csv

Used for the Funding & Burden dashboard.

| Column | Description |
|---|---|
| `category` | Deal category, such as megadeal, non-megadeal, or all deals. |
| `deal_count` | Number of deals in the category. |
| `total_funding_usd_bn` | Total funding value in billions of US dollars. |
| `deal_count_share_pct` | Share of total deal count represented by the category. |
| `funding_share_pct` | Share of total funding represented by the category. |

## regional_disease_burden_dashboard.csv

Used for the Funding & Burden dashboard.

| Column | Description |
|---|---|
| `region` | Region or country-level grouping. |
| `total_dalys_millions` | Total disease burden in millions of DALYs. |
| `avg_dalys_millions` | Average disease burden in millions of DALYs. |
| `burden_rank` | Rank of region by total disease burden, if included in the export. |

---

# 8. Key Data Quality Notes

- No major missing-value issues were identified during the initial data quality review.
- No full duplicate rows were found.
- Date columns were converted into datetime format where applicable.
- The main analysis period was restricted to 2010–2025.
- One 2009 biotech funding record was excluded from the main analysis period.
- 2026 records were excluded from main trend analysis due to possible partial-year coverage.
- Company sponsor naming inconsistencies were standardized where needed, such as mapping `J&J` to `Johnson & Johnson` and `BMS` to `Bristol-Myers Squibb`.

---

# 9. Interpretation Notes

This data dictionary documents the structure and analytical use of the datasets, but it does not imply that all fields should be interpreted as causal indicators.

Several metrics are analytical proxies:

- estimated commercial output
- innovation gap score
- estimated stock impact
- disease-to-therapy mapping
- approval productivity per R&D spending

These metrics are useful for comparative analysis but should be interpreted with caution.

The purpose of the project is to identify patterns and possible signals, not to make definitive causal claims.
