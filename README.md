# The Impact of Regional Safety and Educational Attainment on Mental Health: A Multi-Factor Analysis

## Project Overview

This project investigates how regional factors, specifically state-level educational attainment and crime rates, influence individual mental health outcomes in the United States. Using synthetic EHR data linked with public datasets, a multi-level analytical framework was applied to assess the interplay between individual education, regional safety, and depressive symptoms.

## Motivation

Mental health is shaped not only by personal factors but also by broader social determinants. Understanding how community-level variables such as crime and education interact with individual characteristics is crucial for informing public health strategies and interventions.

## Data Sources

- **Synthetic EHR Database**: Simulated patient data following the OMOP Common Data Model, including demographics, clinical conditions, medications, and observations.
- **Public Datasets**:
  - U.S. Census Bureau Educational Attainment Data
  - FBI Crime Data Explorer
  - County Health Rankings & Roadmaps
  - U.S. Bureau of Economic Analysis Socioeconomic Indicators

## Research Questions

1. Is regional safety (measured by crime rates) negatively associated with mental health outcomes?
2. Is higher educational attainment positively associated with mental health outcomes?
3. Does educational attainment moderate the relationship between crime rates and mental health outcomes?

## Methods

- **Data Integration**: Merging individual-level synthetic EHR data with state-level public datasets through relational database structures.
- **Statistical Analyses**:
  - Ordinary Least Squares (OLS) regression
  - Logistic regression for binary outcomes (suicidal ideation, depression diagnosis)
  - Generalized Additive Models (GAMs) for nonlinear interaction analysis
- **Software**: Python 3.12.3 with `pandas`, `statsmodels`, `scipy`, `sqlalchemy`, and `pygam`

## Key Findings

- **Regional Safety**: No significant direct association was found between state-level crime rates and individual depression severity.
- **Educational Attainment**: Individual-level and state-level education did not independently predict depression severity, but a significant interaction effect was identified. College-educated individuals experienced better mental health outcomes in highly educated states.
- **Moderation Effect**: Generalized Additive Models revealed that the protective effect of education on suicide risk diminishes in high-crime environments, suggesting complex, context-dependent interactions.

## Database Schema

- EHR Tables: `final_person`, `final_concept`, `final_condition_occurrence`, `final_drug_exposure`, `final_measurement`, `final_observation`
- Public Tables: `mental_health_data`, `Crimes_Against_Offenses`, `Annual_Summary_Statistics`, `Edu_Level_Survey`, `Edu_Level_Survey_5_years`

Each table is linked via unique IDs (e.g., `person_id`, `FIPS`, `GEO_ID`) to allow integrated multi-level analyses.

## Limitations

- Limited geographic scope (eight states)
- Cross-sectional design restricts causal inference
- Potential unmeasured confounding factors not captured
- State-level aggregation may obscure local-level variations

## Future Directions

- Expand to a larger and more granular geographic dataset (e.g., county-level)
- Incorporate longitudinal data for causal inference
- Include additional social and environmental factors (e.g., perceived safety, healthcare access)
- Explore further nonlinear and subgroup analyses
