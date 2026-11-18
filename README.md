# Loan Risk Data Analysis Project

## Project Overview

This project focuses on analyzing loan applications and identifying patterns associated with loan default risk.

Building on a previously developed SQL Data Warehouse project, this analysis explores applicant characteristics, loan attributes, credit profiles, and financial indicators to understand how they relate to default rates.

The project uses SQL for data analysis and Power BI for data visualization and reporting.

The main objective is to transform structured loan application data into meaningful analytical insights and communicate the findings through an interactive business intelligence dashboard.

## Project Objectives

- Analyze loan application and default distributions.
- Examine default rates across different loan types and purposes.
- Investigate relationships between applicant characteristics and loan default.
- Compare default rates across credit types, loan amounts, loan terms, and occupancy types.
- Explore the relationship between applicant income and loan amount.
- Identify unusual patterns and data characteristics that may require further investigation.
- Present analytical findings through a Power BI dashboard.

## Tools & Technologies

- **PostgreSQL:** SQL-based data analysis and querying.
- **Power BI:** Data visualization and dashboard development.
- **DAX:** Measures and calculated columns.
- **SQL:** Aggregations, conditional calculations, segmentation, and analytical queries.

## Project Workflow

1. **Data Warehouse:** The original loan dataset was previously processed and organized into a dimensional data warehouse.
2. **Data Analysis:** SQL queries were used to investigate loan applications, default rates, applicant profiles, and financial characteristics.
3. **Data Exploration:** Numerical and categorical variables were examined, and relevant groups and segments were created.
4. **Visualization:** The analytical results were transferred to Power BI.
5. **Reporting:** Two dashboard pages were developed to present the overall loan risk profile and more detailed applicant and credit characteristics.

## Dashboard

The Power BI report consists of two main pages.

### 1. Loan Default Analysis Overview

This page provides a high-level overview of loan applications and default behavior.

It includes:
- Total loan applications and default applications.
- Default rate and average loan amount.
- Application distribution by default status.
- Default rates by loan type, income segment, age group, and region.
- Applicant distribution by gender and joint application status.

![Loan Default Analysis Overview](images/overview-dashboard.png)

### 2. Applicant & Credit Profile

This page focuses on the relationship between applicant characteristics, credit attributes, and loan default.

It includes:
- Average income, average credit score, and average interest rate.
- Default rate by loan amount.
- Default rate by credit type.
- Default rate by loan term.
- Default rate by debt burden segment.
- Default rate by occupancy type.
- Scatter plot showing income and loan amount by default status.

![Applicant & Credit Profile](images/applicant-credit-profile.png)

## Key Analytical Findings

The analysis covers **148,670 loan applications**, of which **36,639 resulted in default**.

| Metric | Value |
|---|---:|
| Total Applications | 148,670 |
| Default Applications | 36,639 |
| Non-Defaulted Applications | 112,031 |
| Default Rate | 24.64% |
| Average Loan Amount | 331,117.74 |

### Applicant Characteristics

- Approximately 29% of applications were associated with male applicants.
- Approximately 23% were associated with female applicants.
- Approximately 21% represented joint applications.
- Approximately 26% had unknown gender information.

### Loan Type

Default rates differed across loan types:

| Loan Type | Default Rate |
|---|---:|
| Business / Commercial | 34.54% |
| Personal | 23.04% |

Business and commercial loan applications showed a higher default rate than personal loan applications.

### Credit Type

A substantial difference was observed across credit information providers.

| Credit Type | Default Rate |
|---|---:|
| Equifax | 99.99% |
| CRIF Credit Bureau | 16.23% |
| Experian | 15.99% |
| Credit Information Bureau | 15.80% |

Equifax displayed an exceptionally high default rate compared with the other credit types. This result was also examined through SQL queries.

### Occupancy Type

| Occupancy Type | Default Rate |
|---|---:|
| Investment Residence | 29.99% |
| Secondary Residence | 27.13% |
| Primary Residence | 24.30% |

Investment residence applications showed the highest default rate among the occupancy categories.

### Loan Term

| Term Group | Default Rate |
|---|---:|
| Unknown | 36.59% |
| Short Term | 18.72% |
| Medium Term | 23.13% |
| Long Term | 24.91% |

Applications with missing loan term information had a notably higher default rate than applications with a known term.

### Debt Burden Segment

| Segment | Default Rate |
|---|---:|
| Low | 23.08% |
| Medium | 23.30% |
| High | 29.03% |

The high debt burden segment showed a higher default rate than the low and medium segments.

### Loan Amount Analysis

Loan amounts were divided into ranges to investigate how default rates varied across different borrowing levels.

Some notable results included:

- Below 100K: 37.10%
- 500K–600K: 19.68%
- 800K–1M: 41.67%
- 1M–1.5M: 45.43%
- 1.5M+: 65.96%

The highest loan amount category contained only 141 applications. Therefore, its default rate should be interpreted with caution.

### Income and Loan Amount Relationship

A scatter plot was developed to examine the relationship between applicant income, loan amount, and default status.

The analysis also identified a positive correlation of approximately 0.616 between income and loan amount in the log-log analysis.

The visualization allows comparison of defaulted and non-defaulted applications across income and loan amount levels.

## Data Characteristics & Analytical Limitations

Several findings require careful interpretation:

- **Unknown Categories:** Some applications contain missing categorical information, such as age or loan term. These records were retained as separate categories rather than excluded from the analysis.
- **Credit Type:** The exceptionally high default rate associated with Equifax was verified through SQL analysis. The underlying reason for this difference is not established by the analysis.
- **Debt-to-Income Ratio:** The debt burden indicator used in this project was calculated as `LN(loan_amount / final_income)`. It should not be interpreted as a conventional debt-to-income ratio.
- **Small Sample Groups:** Some high loan amount categories contain relatively few applications, which can make their default rates less representative.
- **Correlation vs. Causation:** Observed relationships between variables and default rates do not establish causal relationships.

## Conclusion

This project demonstrates how SQL-based analysis and business intelligence tools can be used together to investigate loan default patterns.

The analysis highlights differences across loan types, credit providers, occupancy categories, loan terms, debt burden segments, and loan amount ranges.

The resulting Power BI report provides a structured view of loan application characteristics and default behavior, while also highlighting unusual patterns and analytical limitations that should be considered when interpreting the results.

## Related Project

This analysis builds on a previously developed SQL Data Warehouse project:

[SQL Loan Risk Data Warehouse Project](https://github.com/zeynepican/sql-loan-risk-data-warehouse-project)
