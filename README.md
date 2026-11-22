# Data Science Jobs Salary Analysis | Excel Power Query

## Project Overview

This project uses **Microsoft Excel Power Query** to prepare, transform, combine and analyse a dataset of data science job listings. The analysis explores how advertised salary ranges vary by US state, company size and job role.

The workbook contains four salary-summary tables, a state lookup table and the job-listings dataset. The summaries are designed to answer specific questions about salary patterns and the distribution of job opportunities.

## Objectives

- Prepare job-listing data for analysis using Power Query.
- Analyse job counts and average minimum and maximum salary estimates.
- Compare salary ranges across states, company sizes and role types.
- Combine datasets using state information as the matching field.
- Practise query referencing, duplication, grouping, aggregation and merging.

## Tools and Techniques

**Tool:** Microsoft Excel – Power Query Editor

**Power Query techniques used:**
- Referencing an existing query to create a connected query.
- Duplicating a query to create an independent version for transformation.
- Grouping rows by one or more fields.
- Aggregating records using counts and averages.
- Merging queries/datasets using state abbreviations.
- Expanding merged columns to bring relevant state information into the job-listings data.

## Workbook Structure

| Worksheet | Preparation method | Purpose |
|---|---|---|
| `Salary by state_ref` | Referenced from the original data query | Summarises job counts and average salary estimates by state. |
| `Salary by size & row type_dup` | Created using a duplicate of the data query | Compares job counts and average salary estimates by company size and role type. |
| `Salary by size_ref` | Referenced from the original data query | Summarises job counts and average salary estimates by company size. |
| `Salary by role type_dup` | Created using a duplicate of the data query | Summarises job counts and average salary estimates by role type. |
| `Raw_DS_jobs` | Job-listings dataset with state fields incorporated | Contains the job-level data used for the analysis, including state abbreviation and state name fields. |
| `states` | State lookup dataset | Provides the full state name and its two-letter USPS abbreviation. |
| `Sheet1` | Empty worksheet | No analysis is presented on this worksheet. |

## Questions and Findings

### 1. Salary by State

**Question: How do data science job opportunities and average salary estimates differ across states?**

The analysis groups job listings by state and calculates the number of listings and the average minimum and maximum salary estimates.

Key findings:
- **California** has the largest number of listings, with **141**.
- **Virginia** follows with **84** listings.
- **Massachusetts** has **58** listings, while **New York** has **47**.
- **Delaware** has the highest average salary estimates in the table: **212,000 average minimum** and **331,000 average maximum**. However, this result is based on only **one listing**, so it should not be treated as representative of the state market.
- Among states with larger numbers of listings, **North Carolina** has a notably high average minimum estimate of **121,222**, based on **nine listings**.

**Interpretation:** California leads in the volume of listings, but the state with the highest average salary estimates is not necessarily the state with the most opportunities. Small sample sizes can produce unusually high or low averages.

### 2. Salary by Company Size

**Question: How does company size relate to the number of job opportunities and average salary estimates?**

The analysis groups job listings by company-size category.

Key findings:
- Companies with **51 to 200 employees** have the most listings, at **127**.
- Companies with **1,001 to 5,000 employees** have **104** listings.
- Companies with **1 to 50 employees** have **83** listings.
- The **5,001 to 10,000 employees** category has the highest average minimum salary estimate, at **104,000**.
- The **51 to 200 employees** category has the highest average maximum salary estimate, at approximately **152,244**.

**Interpretation:** The 51–200 employee category has the largest number of listings and the highest average maximum salary estimate. However, salary estimates do not increase consistently with company size.

### 3. Salary by Role Type

**Question: Which job role has the most listings, and how do average salary estimates compare across roles?**

The analysis groups job listings by role type and calculates the count and average minimum and maximum salary estimates.

Key findings:
- **Data Scientist** is the most frequently represented role, with **415** listings in the summary.
- The **Other** category has the highest average minimum salary estimate, at approximately **102,929**.
- Data Scientist and Other both have the highest average maximum salary estimate in the summary, at **331,000**.
- Data Analysts have an average minimum estimate of approximately **93,532** and an average maximum estimate of **225,000**.
- Data Engineers have an average minimum estimate of approximately **94,106** and an average maximum estimate of **201,000**.
- Machine Learning Engineers have an average minimum estimate of **89,100** and an average maximum estimate of **201,000**.

**Interpretation:** Data Scientist roles dominate the dataset by listing count. The Other category has the highest average minimum estimate, while Data Scientist and Other share the highest average maximum estimate. These are averages of salary-range endpoints, not actual salaries earned by employees.

### 4. Salary by Company Size and Role Type

**Question: How do salary estimates for different job roles vary across company-size categories?**

This analysis groups listings using two fields: company size and role type.

Key findings:
- The largest group is **Data Scientist roles at companies with 51 to 200 employees**, with **88** listings.
- Within that group, the average minimum salary estimate is approximately **106,307**, and the average maximum is approximately **158,386**.
- The highest average minimum estimate in this table is **138,000** for Data Engineer roles at companies with **5,001 to 10,000 employees**. This is based on only **one listing**, so it should be interpreted cautiously.
- Data Scientist roles appear across all seven company-size categories.

**Interpretation:** Data Scientist roles are represented across a wide range of company sizes. The comparison also shows why it is useful to analyse role type and company size together: salary patterns can differ between roles even within the same company-size category.

## Data Merging: Job Listings and State Lookup

The workbook also demonstrates merging information from different datasets using state information.

The `states` lookup table contains:
- The full state name.
- The corresponding two-letter USPS state abbreviation.

The `Raw_DS_jobs` dataset contains job-listing information and state fields, including `State Abbr` and `State Name`.

The state abbreviation provides a common matching field for connecting the job-listings data to the state lookup data. In Power Query, the merge can be performed by matching the job dataset's state abbreviation to the lookup table's `2-letter USPS` field, then expanding the required state information.

This makes state information more consistent and supports state-level grouping and analysis.

## Important Data Notes and Limitations

- The workbook's salary columns are labelled **Avg Min Salary** and **Avg Max Salary**. They represent averages of the lower and upper endpoints of the advertised salary ranges; they should not be interpreted as actual employee earnings.
- The workbook does not explicitly label the salary currency in the summary tables. Confirm the source dataset's currency before presenting the figures externally.
- Some state and role/company-size groups have very few listings. Averages based on one or two observations may not represent typical market salaries.
- The role-type summary totals **628** listings, while the state summary, company-size summary and combined company-size/role summary each total **610**. This difference should be checked in Power Query before treating the role-type counts as directly comparable with the other summaries.
- The `Other` role category combines job titles that were not classified into the named role categories. Its results may therefore represent a diverse set of positions.

## Skills Demonstrated

- Microsoft Excel
- Power Query data transformation
- Query referencing and duplication
- Data grouping and aggregation
- Data merging and lookup tables
- Salary and job-market analysis
- Data interpretation and communicating findings
