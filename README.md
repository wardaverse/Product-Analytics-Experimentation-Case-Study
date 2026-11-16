# Product Analytics Case Study: Funnel Optimization, Retention, Cohort Analysis & A/B Testing

**Warda Shafiq \| Product Analytics · Data Science · Business
Intelligence**

**SQL · Python · Power BI · Statistical Analysis · Experimentation**

An end-to-end product analytics project examining user acquisition,
engagement, conversion, and retention for a simulated European mobility
platform. The project follows a complete analytical workflow,
translating business questions into measurable product insights through
SQL-based analysis, Python statistical modeling, data quality
validation, and interactive Power BI reporting.

The analysis covers conversion funnel performance, user segmentation,
cohort-based retention, feature adoption, and controlled
experimentation. It concludes with evidence-based recommendations
designed to improve product conversion, user engagement, and revenue
performance.

> **Data & Research Disclaimer:** This project uses entirely synthetic
> data generated with a fixed random seed. It contains no real customer
> records or personally identifiable information. All metrics and
> findings are simulated and demonstrate analytical methodology rather
> than actual commercial performance.

------------------------------------------------------------------------

## 30-Second Project Overview

  -----------------------------------------------------------------------
  Deliverable                         Description
  ----------------------------------- -----------------------------------
  **SQL Analytics**                   10 analytical SQL scripts covering
                                      business KPIs, conversion funnels,
                                      retention, cohorts, segmentation,
                                      and A/B testing using CTEs and
                                      window functions

  **Python Analysis**                 6 Jupyter notebooks covering
                                      exploratory analysis, retention
                                      curves, funnel segmentation,
                                      hypothesis testing, and statistical
                                      confidence intervals

  **Power BI Dashboard**              Six-page interactive report with 27
                                      DAX measures and 56 visual elements

  **Data Quality Framework**          23 validation checks and 25
                                      automated pytest tests, all passing

  **Business Intelligence**           Documented analytical findings,
                                      product performance insights, and
                                      actionable business recommendations

  **Project Documentation**           Reproducible codebase, data
                                      dictionary, analytical scripts, and
                                      supporting visualizations
  -----------------------------------------------------------------------

### Selected Analytical Visualizations

```{=html}
<table>
```
```{=html}
<tr>
```
```{=html}
<td width="50%">
```
`<img src="images/23_conversion_funnel.png" alt="User conversion funnel"/>`{=html}
```{=html}
</td>
```
```{=html}
<td width="50%">
```
`<img src="images/32_experiment_dashboard.png" alt="A/B testing results"/>`{=html}
```{=html}
</td>
```
```{=html}
</tr>
```
```{=html}
<tr>
```
```{=html}
<td width="50%">
```
`<img src="images/21_cohort_retention_heatmap.png" alt="Cohort retention heatmap"/>`{=html}
```{=html}
</td>
```
```{=html}
<td width="50%">
```
`<img src="images/27_funnel_by_channel.png" alt="Conversion funnel by acquisition channel"/>`{=html}
```{=html}
</td>
```
```{=html}
</tr>
```
```{=html}
</table>
```

------------------------------------------------------------------------

## 1. Business Problem & Analytical Objectives

The project investigates five core dimensions of product performance
through the following business questions:

1.  **Conversion Optimization:** At which stages of the user journey
    does the platform experience the greatest conversion leakage?
2.  **Acquisition Effectiveness:** Which acquisition channels and
    platforms attract users with the highest conversion rates and
    customer value?
3.  **Retention & Engagement:** How does retention evolve across signup
    cohorts, and which product engagement patterns correlate with
    long-term user activity?
4.  **Product Experience:** How do user behavior and conversion
    performance differ across platforms and customer segments?
5.  **Experimentation:** Did simplifying the booking experience produce
    a statistically significant improvement in conversion and revenue
    per user?

The objective is to move beyond descriptive reporting and demonstrate
how product analytics can support prioritization, experimentation, and
strategic decision-making.

## 2. Dataset & Data Architecture

The analytical environment consists of three interconnected datasets
generated specifically for this case study.

  ------------------------------------------------------------------------
  Dataset                                    Records Analytical Grain
  --------------------- ---------------------------- ---------------------
  `users`                                      5,000 One record per user,
                                                     including country,
                                                     platform, acquisition
                                                     channel, age group,
                                                     and experiment
                                                     assignment

  `events`                                   141,813 Individual user
                                                     events across 15
                                                     event types, from app
                                                     opening to booking
                                                     completion

  `experiments`                                5,000 One record per user
                                                     participating in the
                                                     simplified booking
                                                     flow experiment
  ------------------------------------------------------------------------

**Analysis period:** January 2024 -- June 2025.

The event-level dataset supports behavioral analysis, while user-level
and experiment-level tables enable segmentation, cohort tracking, and
controlled experimentation.

Full data dictionary: `data/README.md`

## 3. Key Analytical Findings

The analysis produced several insights into acquisition quality,
conversion efficiency, retention behavior, and product experimentation.

### Executive Performance Metrics

  Metric                                  Result
  --------------------------------- ------------
  Completed Bookings                       2,731
  Simulated Revenue                   €39,589.80
  User Conversion Rate                     28.7%
  Average Revenue per User (ARPU)          €7.92
  Day 1 Retention                          10.2%
  Day 7 Retention                           9.3%
  Day 30 Retention                          7.1%

### Finding 1: The Primary Conversion Bottleneck Occurs Before Booking Initiation

Although 69.2% of users initiate a search, only 33.1% progress to
booking initiation, representing a 52.1% drop-off between these stages.

By comparison, 86.5% of users who initiate a booking successfully
complete it.

**Business implication:** The most significant optimization opportunity
lies in search discovery, property/service comparison, and the
transition from search results to booking initiation rather than
checkout optimization alone.

### Finding 2: Acquisition Quality Outperforms Acquisition Volume

Acquisition channels demonstrate substantial differences in user value.

  Acquisition Channel     Conversion Rate     ARPU
  --------------------- ----------------- --------
  Referral                          40.0%   €13.03
  Paid Search                       23.5%    €5.43
  Paid Social                       21.0%      ---

Referral users demonstrate considerably stronger conversion and
monetization performance.

**Business implication:** Acquisition strategies should prioritize
customer quality and downstream value rather than optimizing exclusively
for registration volume.

### Finding 3: Platform Experience Influences Conversion Performance

  Platform     Conversion Rate
  ---------- -----------------
  iOS                    30.0%
  Android                28.8%
  Web                    24.0%

The Web experience underperforms both mobile platforms, suggesting
potential usability, performance, or journey-friction issues.

**Business implication:** Investigate platform-specific behavior and
prioritize improvements to the Web conversion journey.

### Finding 4: Product Engagement Features Correlate with Higher Retention

Day 30 retention increases from 2.0% among users who adopted none of the
three measured engagement features to 14.7% among users who adopted all
three.

This represents a substantial observational difference.

**Business implication:** Feature adoption may be an important retention
indicator. However, correlation does not establish causation; controlled
experimentation is required before attributing retention improvements to
these features.

### Finding 5: Simplifying the Booking Flow Produces Statistically Significant Improvements

The A/B experiment evaluates the impact of a simplified booking
experience on conversion and revenue performance.

  Metric              Control   Treatment                Difference
  ----------------- --------- ----------- -------------------------
  Users                 2,484       2,516                       ---
  Converted Users         668         766                       +98
  Conversion Rate      26.89%      30.45%   +3.55 percentage points
  ARPU                  €7.02       €8.80                    +€1.78

**Statistical validation:**

-   Conversion uplift: +13.2% relative improvement.
-   95% confidence interval for conversion difference: 1.05--6.06
    percentage points.
-   Two-proportion z-test: z = 2.78, p = 0.006.
-   ARPU difference: +€1.78.
-   Welch's t-test for ARPU: p \< 0.001.

The experiment provides statistically significant evidence of improved
conversion and revenue per user within the simulated dataset.

### Strategic Recommendations

1.  **Optimize the conversion funnel:** Prioritize search-to-booking
    progression and investigate friction points in the Web experience.
2.  **Improve acquisition efficiency:** Allocate more resources toward
    high-performing referral channels while refining paid acquisition
    targeting.
3.  **Scale validated product improvements:** Roll out the simplified
    booking experience while monitoring conversion, ARPU, and downstream
    user behavior.
4.  **Strengthen retention strategies:** Investigate engagement-feature
    adoption and validate retention interventions through controlled
    experiments.
5.  **Establish continuous measurement:** Monitor acquisition quality,
    conversion, retention, and monetization through an integrated
    product analytics framework.

------------------------------------------------------------------------

## 4. SQL Analytics: Funnel Analysis & Window Functions

The SQL layer provides the foundation for extracting product performance
metrics and identifying behavioral patterns across the user journey.

The following example demonstrates the use of CTEs, `LAG()`, and
`FIRST_VALUE()` to calculate funnel progression and stage-level
abandonment.

**Source:** `sql/04_funnel_analysis.sql`

``` sql
WITH funnel_counts AS (
    SELECT 'signup' AS stage,
           1 AS stage_order,
           COUNT(*) AS users_reached
    FROM users

    UNION ALL

    SELECT 'search_started', 2,
           COUNT(DISTINCT user_id)
    FROM events
    WHERE event_name = 'search_started'

    UNION ALL

    SELECT 'booking_started', 3,
           COUNT(DISTINCT user_id)
    FROM events
    WHERE event_name = 'booking_started'

    UNION ALL

    SELECT 'booking_completed', 4,
           COUNT(DISTINCT user_id)
    FROM events
    WHERE event_name = 'booking_completed'
),

funnel_with_lag AS (
    SELECT
        stage,
        stage_order,
        users_reached,
        LAG(users_reached)
            OVER (ORDER BY stage_order) AS prev_stage_users,
        FIRST_VALUE(users_reached)
            OVER (ORDER BY stage_order) AS top_of_funnel_users
    FROM funnel_counts
)

SELECT
    stage,
    users_reached,
    ROUND(
        100.0 * users_reached / top_of_funnel_users, 1
    ) AS pct_of_top,
    ROUND(
        100.0 * (prev_stage_users - users_reached)
        / prev_stage_users, 1
    ) AS drop_off_pct
FROM funnel_with_lag
ORDER BY stage_order;
```

### Funnel Analysis Results

  Stage                 Users Reached   \% of Initial Users   Stage Drop-off
  ------------------- --------------- --------------------- ----------------
  Signup                        5,000                100.0%              ---
  Search Started                3,460                 69.2%            30.8%
  Booking Started               1,657                 33.1%            52.1%
  Booking Completed             1,434                 28.7%            13.5%

### SQL Analytical Modules

  -----------------------------------------------------------------------
  Script                              Analytical Focus
  ----------------------------------- -----------------------------------
  `00_schema.sql`                     Database schema, relationships,
                                      primary keys, and indexes

  `01_data_quality.sql`               Missing values, duplicate records,
                                      referential integrity, and
                                      validation rules

  `02_business_overview.sql`          User, event, and booking
                                      performance across segments

  `03_kpi_dashboard.sql`              Conversion, ARPU, ARPPU, AOV, and
                                      monthly performance metrics

  `04_funnel_analysis.sql`            Funnel progression, conversion
                                      rates, and abandonment

  `05_retention.sql`                  D1, D7, D30 retention and churn
                                      analysis

  `06_cohort_analysis.sql`            Monthly signup cohorts and
                                      retention patterns

  `07_feature_adoption.sql`           Feature adoption and associated
                                      retention behavior

  `08_segmentation.sql`               Acquisition channel, platform, and
                                      geographic segmentation

  `09_ab_testing.sql`                 Experiment sample sizes, conversion
                                      uplift, and statistical
                                      calculations

  `10_business_recommendations.sql`   Supporting metrics for strategic
                                      recommendations
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 5. Python: Statistical Analysis & Exploratory Data Analytics

Python supports the analytical workflow through exploratory analysis,
behavioral visualization, statistical testing, and validation.

**Six Jupyter notebooks cover:**

-   Exploratory data analysis and distribution profiling.
-   User behavior and conversion funnel segmentation.
-   Cohort-based retention curves.
-   Feature adoption and engagement patterns.
-   A/B testing using two-proportion z-tests.
-   Welch's t-tests, statistical significance, and 95% confidence
    intervals.

The statistical workflow emphasizes interpretation of experimental
results alongside practical product implications.

## 6. Power BI: Interactive Product Analytics Dashboard

The Power BI report consolidates the analytical findings into an
executive-facing reporting environment.

**Six dashboard pages:**

  -----------------------------------------------------------------------
  Dashboard Page                      Key Components
  ----------------------------------- -----------------------------------
  Executive Overview                  KPI cards, performance trends, and
                                      interactive filters

  User Behaviour                      Engagement patterns and user
                                      segmentation

  Product Funnel                      Conversion stages, abandonment, and
                                      funnel performance

  Retention Analysis                  Cohort matrix, D1/D7/D30 retention

  Experiment Analysis                 Control vs. treatment, conversion
                                      uplift, and ARPU

  Executive Recommendations           Key findings and strategic
                                      priorities
  -----------------------------------------------------------------------

**Dashboard specifications:**

-   27 DAX measures.
-   56 visual elements.
-   Interactive slicers and cross-filtering.
-   Cohort-based retention analysis.
-   Experiment performance comparisons.

Selected DAX measures include:

`Day 7 Retention %` · `Cohort Retention %` · `Booking Start Rate %` ·
`Abandonment Rate %` · `Experiment Uplift pp` · `ARPU Uplift %`

**Report:** `dashboard/Product_Analytics_Dashboard.pbix`

Open the file using Power BI Desktop.

------------------------------------------------------------------------

## 7. Data Quality & Automated Testing

Analytical reliability is supported through a dedicated validation
framework.

  -----------------------------------------------------------------------
  Component                           Coverage
  ----------------------------------- -----------------------------------
  SQL Validation                      Missing values, duplicates, orphan
                                      records, date constraints, and
                                      revenue rules

  Python Validation                   23 automated data-quality checks

  Test Automation                     25 pytest tests

  Reproducibility                     Fixed random seed for consistent
                                      synthetic data generation
  -----------------------------------------------------------------------

All 23 validation checks and 25 automated tests pass.

Relevant files:

-   `src/validate_data.py`
-   `tests/`

------------------------------------------------------------------------

## 8. Technology Stack

  -----------------------------------------------------------------------
  Category                            Technologies
  ----------------------------------- -----------------------------------
  Querying & Data Analysis            SQL, SQLite

  Programming                         Python

  Data Manipulation                   pandas, NumPy

  Statistical Analysis                SciPy, hypothesis testing,
                                      confidence intervals

  Data Visualization                  Matplotlib, Seaborn

  Business Intelligence               Power BI, DAX

  Testing & Validation                pytest

  Development Environment             Jupyter Notebook, Git
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 9. Repository Structure

``` text
product-analytics-case-study/
│
├── data/
│   ├── raw/              # Synthetic datasets
│   ├── processed/        # Processed analytical database
│   └── README.md         # Data dictionary
│
├── src/
│   ├── generate_data.py
│   ├── validate_data.py
│   ├── build_database.py
│   ├── run_sql.py
│   └── EDA helpers
│
├── sql/                  # SQL analytical scripts
├── notebooks/            # Six Python notebooks
├── images/               # Exported analytical visualizations
├── dashboard/            # Power BI report
├── insights/             # Findings and recommendations
├── tests/                # Automated pytest suite
│
├── requirements.txt
└── README.md
```

------------------------------------------------------------------------

## 10. Reproducibility & Execution

**Prerequisites:** Python 3.10+

Clone the repository and install the dependencies:

``` bash
git clone https://github.com/YOUR-GITHUB-USERNAME/product-analytics-case-study.git

cd product-analytics-case-study

pip install -r requirements.txt
```

Execute the analytical workflow:

``` bash
# Generate synthetic datasets
python src/generate_data.py

# Run data quality validation
python src/validate_data.py

# Execute automated tests
python -m pytest tests

# Build the SQLite analytical database
python src/build_database.py

# Execute an individual SQL analysis
python src/run_sql.py sql/04_funnel_analysis.sql

# Launch the analytical notebooks
jupyter notebook notebooks/
```

The fixed random seed (42) ensures that the synthetic datasets can be
regenerated consistently.

------------------------------------------------------------------------

## 11. Future Enhancements

Potential extensions to the analytical framework include:

-   **Cloud Data Warehousing:** Migrate the SQL environment to BigQuery
    or Snowflake.
-   **Analytics Engineering:** Introduce dbt for modular
    transformations, testing, and documentation.
-   **Advanced Experimentation:** Incorporate statistical power
    analysis, minimum detectable effects, and sample-size estimation.
-   **Dashboard Development:** Expand Power BI with drill-through
    functionality and deeper segment-level analysis.
-   **Predictive Analytics:** Explore churn prediction, conversion
    propensity, and user lifetime value modeling.

------------------------------------------------------------------------

## About the Project

**Warda Shafiq**\
Product Analytics \| Data Science \| AI & Technology

LinkedIn: https://www.linkedin.com/in/warda-shafiq-45736038/\
GitHub: [\[YOUR-GITHUB-USERNAME\]](https://github.com/wardaverse)

*Building data-driven products and translating complex analytical
insights into measurable business and product outcomes.*
