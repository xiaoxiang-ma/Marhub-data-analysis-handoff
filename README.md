# Marhub-data-analysis-handoff

### Key Objectives:
- Find out indicators of a high vulnerability refugee (Predicting Vulnerability Threshold to be either "High" or "Low).
- Find out indicators of a short/long IRAP application processing time.

### Issues:
- Very Skewed data (only about 2% of data are above thresholds)
    - Upsampling minority (Vulnerability Threshold: Above).
    - Downsampling majority (Vulnerability Threshold: Below).
    - Above attempts were not helpful due to such a high skewness.
- High percentages of null variables
    - Logically due to different progressions in the chatbot question tree (Not all users are asked the same question).
    - Resolved by removing variables with >70% of null values.
    - Future: Could try seprating the refugees by groups and performing modelling separately.

- Inconsistent data formats, e.g. datetime strings, arabic, english... 
    - Manually fixed after data collection.
    - Submitted report/guide on what to fix in the stage of data generation.
- Inconsistent/Updating data source, e.g. Podio/Zendesk/Irap
    - 3 different widths of datasheets
    - Manual merge with logic discussed
    - Data loss due to missing columns
    - FUTURE: Establish *single* data source with *consistent* format 



### Methods used:
- Pearson correlation
- P-value analysis
- Variable selection
- Logistic regression
- Random Forest

### Key findings:
- Variables indicative of vulnerability
    - Inconclusive, no statistically significant variables are found 
    
- Variables indicative of processing time
    - LPPN Score
    - Traumatic incident score
    - Aggr 2 Threat Within Last 6 Months
    - Aggr 2 SVT Rating
    - Aggr 2 Reason Unable to Move
    - Medical Condition 1 SVT

### Next Steps
- Establish *single* data source with *consistent* format.
- Increase the size of the data by at least ten folds to remedy the insane skewness.
- Group refugees by the series of questions they are asked, and then train many models for each group. Split into subgroups instead of trying to build one-size-fit-all model.