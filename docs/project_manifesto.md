# Project Manifesto  
## Global Healthcare & Pharma Innovation Gap Case Study

## Purpose

This project was designed as a healthcare analytics case study, not only as a traditional exploratory data analysis project.

The main purpose is to investigate whether pharmaceutical innovation activity aligns with global disease burden. Instead of only describing trends in revenue, R&D spending, drug approvals, clinical trials, biotech funding, and disease burden, this project aims to connect these dimensions into a decision-oriented analytical framework.

The central question is:

**Are pharmaceutical innovation efforts aligned with the areas of highest global health burden?**

## Case Study Context

The global healthcare and pharmaceutical industry is shaped by multiple forces:

- commercial opportunity
- clinical development risk
- R&D investment capacity
- regulatory approval dynamics
- biotech funding cycles
- disease burden across regions and therapy areas
- market incentives and scientific feasibility

Because of this, pharmaceutical innovation does not always follow disease burden directly. High-burden diseases may not always receive proportional innovation activity, while some therapy areas may attract stronger investment, approval activity, and commercial focus.

This project explores that tension.

## Analytical Objective

The objective of this case study is to move from raw healthcare and pharma datasets toward a structured analytical view of:

- how the pharmaceutical market evolved between 2010 and 2025
- how revenue and R&D spending changed over time
- which companies and segments showed stronger innovation capacity
- which therapy areas dominated drug approvals and estimated commercial output
- how clinical trial success rates varied by therapy area
- how biotech funding was distributed across deal types
- how disease burden differed across regions and disease groups
- where potential innovation gaps may exist

The project does not attempt to prove causality. Instead, it builds an analytical framework to identify patterns, misalignments, and areas that may deserve closer investigation.

## Core Analytical Questions

This case study is guided by the following questions:

1. How did global pharma revenue and R&D spending evolve between 2010 and 2025?

2. Did R&D intensity change meaningfully over time, or did R&D spending grow broadly in line with revenue?

3. Which companies and pharma segments showed the strongest revenue, R&D spending, and R&D intensity patterns?

4. Which therapy areas received the highest number of drug approvals?

5. Which therapy areas showed the strongest estimated commercial output?

6. How did clinical trial success rates differ across therapy areas?

7. Is pharmaceutical innovation activity aligned with global disease burden?

8. Which therapy areas show possible signs of under-prioritization relative to disease burden?

9. How concentrated is biotech funding across deal types and megadeals?

10. Which regions carry the highest disease burden?

## Analytical Approach

The project follows an end-to-end analytics workflow:

1. **Data Quality Review**  
   The datasets were checked for missing values, duplicate rows, data types, date fields, and time coverage.

2. **Exploratory Data Analysis**  
   Initial analysis was performed to understand the structure and behavior of each dataset.

3. **Financial Performance Analysis**  
   Pharma revenue, R&D spending, operating margins, pipeline estimates, and R&D intensity were analyzed across companies, years, and segments.

4. **Drug Approval and Clinical Trial Analysis**  
   Drug approvals were analyzed by year, company, therapy area, drug type, and commercial potential. Clinical trials were analyzed by phase, outcome, therapy area, success rate, and estimated stock impact.

5. **Biotech Funding and Disease Burden Analysis**  
   Biotech funding was analyzed by year, deal type, deal count, average deal size, and megadeal concentration. Disease burden was analyzed across diseases, therapy mappings, regions, and years.

6. **KPI Engineering**  
   Company-level and therapy-area-level KPIs were created to support dashboard development and higher-level interpretation.

7. **Innovation Gap Framework**  
   A custom innovation gap score was created to compare disease burden rank with innovation activity rank.

8. **Dashboard Development**  
   Tableau dashboards were created to communicate the findings through executive-level visuals and case study storytelling.

## Innovation Gap Framework

The most important analytical layer of this project is the innovation gap framework.

The framework compares disease burden with pharmaceutical innovation activity across therapy areas.

The following dimensions were used:

- disease burden rank
- drug approval rank
- estimated commercial output rank
- clinical trial activity rank
- combined innovation activity rank

The innovation gap score is interpreted as follows:

- **Positive score**: possible under-prioritization relative to disease burden
- **Negative score**: stronger innovation concentration relative to disease burden
- **Near-zero score**: closer alignment between burden and innovation activity

This score should be interpreted as an analytical signal, not as a causal conclusion.

## Key Case Study Direction

The project is built around the idea that healthcare analytics should not stop at reporting historical trends.

Revenue growth, R&D spending, approval counts, and funding totals are important, but they become more meaningful when connected to a broader question:

**Does innovation activity reflect global health needs?**

This case study uses data analysis and dashboard storytelling to explore that question.

## Expected Output

The final project output includes:

- cleaned and structured datasets
- exploratory analysis notebooks
- KPI engineering notebooks
- Tableau-ready export files
- Tableau dashboards
- dashboard screenshots
- case study documentation
- final README with problem framing, analytical questions, findings, interpretations, and limitations

## Intended Audience

This project is designed for:

- healthcare analysts
- business intelligence analysts
- pharma and biotech analysts
- data analyst recruiters
- portfolio reviewers
- policy and public health analytics audiences
- anyone interested in the relationship between pharmaceutical innovation and global disease burden

## Positioning

This project should be understood as:

**A healthcare analytics case study using Python, Jupyter Notebook, Tableau, and structured KPI engineering to analyze pharmaceutical innovation alignment with global disease burden.**

It is not only an EDA project.

It is not only a dashboard project.

It is a case study that moves from data exploration to analytical framing, insight development, and decision-oriented storytelling.

## Limitations

The analysis has several important limitations:

- The innovation gap score is a proxy metric and should not be interpreted as proof of underinvestment or neglect.
- Disease-to-therapy-area mapping required assumptions.
- Funding descriptions could not be reliably mapped to therapy areas, so funding was not included directly in the innovation gap score.
- Estimated commercial output is based on peak sales estimates, not realized revenue.
- The main analysis period excludes 2026 because it may represent an incomplete year.
- Regional disease burden is analyzed at a broad regional level, not at detailed country level.
- The analysis identifies patterns and possible signals, but further research would be needed for causal interpretation.

## Guiding Principle

The guiding principle of this project is simple:

**Good analytics should not only show what happened. It should help explain why it matters.**
