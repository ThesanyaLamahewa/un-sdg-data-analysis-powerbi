# UN SDG Analytics Dashboard: Data Ingestion, Cleaning & Visualization

## Overview
This repository contains the end-to-end data analytics pipeline and interactive Power BI dashboard developed to analyze the United Nations Sustainable Development Goals (SDG) Data Repository. The project transforms complex, multi-dimensional global datasets into actionable insights for policymakers and NGOs, focusing on Goal 1 (No Poverty), Goal 2 (Zero Hunger), Goal 3 (Good Health & Well-being), and Goal 13 (Climate Action).

## Technology Stack
- **Database & SQL:** SQL Server, Star Schema Design, Common Table Expressions (CTEs), Views, Stored Procedures
- **BI & Analytics:** Microsoft Power BI, Power Query Editor, DAX
- **Data Engineering:** ETL Pipelines, Data Normalization, Schema Verification, Relationship Modeling
- **Visualization:** Heat Maps, Decomposition Trees, Key Influencers, KPI Cards, Synchronized Cross-Goal Filtering

## Project Workflow
1. **Data Acquisition:** Extracted raw Excel datasets from the UN SDG Data Platform covering four core development indicators.
2. **SQL Staging & Cleaning:** Imported data into SQL Server staging tables, handled missing/inconsistent values, standardized schemas, and removed technical footnotes.
3. **Database Modeling:** Designed and normalized a star schema with shared dimension tables (Countries) and goal-specific fact tables, implementing primary and foreign key constraints.
4. **Advanced SQL Operations:** Developed Views for unified data access, CTEs for ranking and aggregation, and Stored Procedures to serve cleaned, optimized data directly to Power BI.
5. **Power BI Transformation:** Utilized Query Editor for column refinement, data type standardization, custom regional grouping logic, and target comparison flagging.
6. **DAX Implementation:** Engineered time-intelligence measures (YoY change, progress tracking), dynamic country ranking, and top-N value calculations.
7. **Dashboard Development:** Built synchronized, filter-driven visualizations enabling cross-goal comparative analysis, drill-through capabilities, and policy-ready reporting.

## Dashboard Architecture
The Power BI report is organized by SDG, featuring interactive controls (Country, Year, Indicator, Region, Sex slicers) and goal-specific visualizations:
- **Goal 1 (No Poverty):** Filled maps for poverty headcount ratios, heat maps for temporal trends, waterfall charts for net regional changes, and hierarchical matrices.
- **Goal 2 (Zero Hunger):** Decomposition trees for undernourishment drivers, donut charts for food insecurity distribution, and funnel charts for severity progression.
- **Goal 3 (Good Health & Well-being):** Key Influencers analytics for health metric drivers, line charts for mortality/vaccination trends, and gender-disaggregated filtering.
- **Goal 13 (Climate Action):** Pie/Ribbon charts for CO2 emission composition, scatter plots for GDP vs. emissions correlation, tree maps for climate hazard frequency, and gauge charts for target progress.

## Key Insights
- Strong correlation between poverty, hunger, and health outcomes, with Sub-Saharan Africa disproportionately impacted.
- Global hunger metrics show improvement, yet critical hotspots with stalled progress persist.
- Climate vulnerability directly threatens food security, creating compounding development challenges.
- Emissions trajectories reveal a widening gap: developed nations plateau while developing economies see rising contributions.
- Data gaps (e.g., approximately 30% null values for small island states in climate data) highlight ethical considerations in policy modeling and imputation strategies.

## Setup and Usage
1. **Database Initialization:** Execute the provided SQL scripts to create staging tables, dimension tables, fact tables, views, CTEs, and stored procedures in SQL Server.
2. **Data Population:** Load the cleaned UN SDG datasets into the configured database schema.
3. **Power BI Connection:** Open the `.pbix` file, verify the SQL Server connection string, and refresh the dataset to pull data via the configured stored procedure.
4. **Interactive Analysis:** Use report-level slicers to filter by country, year, region, or indicator. Utilize drill-through and decomposition features for granular, evidence-based exploration.

## Challenges and Learnings
- **Schema Redesign:** Transitioned from isolated goal-specific tables to a unified star schema to eliminate redundancy and enable multi-goal analysis.
- **Data Ethics & Cleaning:** Addressed high NULL rates by highlighting rather than imputing missing data to maintain transparency for policy decisions.
- **DAX Optimization:** Refined time-intelligence functions to accurately calculate YoY changes and progress percentages across uneven temporal datasets.
- **Future Improvements:** Implement data quality monitoring dashboards, integrate Power BI bookmarks for guided analytical storytelling, and engage policymakers earlier in the requirements phase.

