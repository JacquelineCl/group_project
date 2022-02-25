# Health Care Disparities - Primary Care Access Analysis

## Overview
![image](https://user-images.githubusercontent.com/67409852/155636523-5070e701-cf1b-4715-b3c7-b440497e2469.png)

## Analysis Results and Summary
Disparities in healthcare are an every day reality in the United States so identifying ares for improvement is crucial for the health and well-being of communities. To answer the question "Are there are counties in the United States that will be underserved by primary care providers in the United States?", a supervised machine learning model is the most appropriate choice. Our model, a logistic regression model using oversampling produces an accuracy score of 99.9% and a r-squared score of 93.8%. This model will predict if a county is under-served/appropriately served 99.9% of the time and can predict new data points 93.8% of the time. 

![image](https://user-images.githubusercontent.com/67409852/155261745-376a9a31-1e1e-4a56-a54e-3296e236bb6c.png)

![image](https://user-images.githubusercontent.com/67409852/155261513-a3b704ee-9511-422c-8186-f2e94538c9d2.png)

Due to the data being split 19:1, the model must include oversampling and the removal of extraneous data. Before the logistic regression model included oversampling, the accuracy score was 96.2%, however, the r-squared score was -.077%, meaning the model was an exceptionally poor fit and could not predict new data points with accuracy. Hyper tuning using SMOTE (Synthetic Minority Oversampling Technique) random oversampling and SMOTEENN (oversampling using SMOTE and cleaning using Edited Nearest Neighbor) using combination sampling does not improve the accuracy score or r-squared score of the model (both remain the same), and undersampling using random undersampling or cluster centroids undersampling lowers the accuracy score and drastically lowers the r-squared score, meaning the model is no longer a good fit and can no longer accurately predict new data. For this reason, undersampling the data should be avoided. 

According to the data, any county with 0.488 primary care physicians per capita or less is "underserved". Out of 3,092 counties, 148 are underserved, or ~5% of all counties, while 2881 counties, or ~95% of counties are appropriately served. While having 95% of the population adequately served is good, 5% of Americans being underserved means over 17 million Americans do not have access to a primary care physician. Solutions to primary care physician disparities might include: (add)

## Machine Learning Model
* Supervised Machine Learning: Logistic Regression
  * We have a question we want to answer, therefore, supervised machine learning is the appropriate choice for this analysis. Logistic Regression will separate the data into two categories, counties that will be underserved by primary care physicians, and counties that will be appropriately served by primary care physicians.
* Accuracy score: 99.9%
* R-squared score: 93.8%

![image](https://user-images.githubusercontent.com/67409852/155629836-9228fc37-9503-4e67-89c9-416490144e39.png)

![image](https://user-images.githubusercontent.com/67409852/155629939-4a7dd7f4-edcb-468a-b076-66d02f3321b4.png)

## Tableau Dashboard

## Presentation

## Tools Used
Jupyter Notebook, Python, Pandas, Mathplotlib, NumPy, Pathlib, Collections, Sklearn.metrics, Tableau, PostgreSQL, Quick DBD

## Conceptual Entity Relationship Diagram 
ERD showing relationships between tabular data sources

![image](https://user-images.githubusercontent.com/67409852/154579881-44d03c5b-2a0f-42bb-b6e0-8a4b2d622aa2.png)

## Database
PostgreSQL 11 used to house and query data

![image](https://user-images.githubusercontent.com/67409852/154578261-ae821af4-9000-4e11-ae76-958689a9ca9c.png)

![image](https://user-images.githubusercontent.com/67409852/154594548-06c1c284-1284-492b-a761-c2453bea59d5.png)

## Data Sources

![image](https://user-images.githubusercontent.com/67409852/155635937-3f600f33-2276-47d8-926e-02c732b3c5a8.png)

## References
https://www.census.gov/popclock/

## Notes

## Roles:

### Jacqueline
* Machine Learning Model
* Tableau Dashboard
* Presentation

### Jenny
* Conceptual ERD
* Income and ZCTA data
* Data Cleaning
* Machine Learning Model and Hyper Tuning
* Analysis Summary
* PostgreSQL Database 

### Tony
* Sources for Income & Population
* Data Cleaning:
  * Physician Data:
    * Filters applied to website prior to downloading csv file:
      * npi
      * grd_yr
      * pri_spec
      * cty
      * st
      * zip
      * ind_assgn
      * grp_assgn
    * The data had to be encoded "ISO-8859-1" in order to work properly
    * Filtering criteria for Primary Care Physician:
      * FAMILY MEDICINE
      * NURSE PRACTITIONER
      * GENERAL PRACTICE
      * PREVENTATIVE MEDICINE
      * EMERGENCY MEDICINE
      * PHYSICIAN ASSISTANT
      * INTERNAL MEDICINE
      * PEDIATRIC MEDICINE
      * OBSTETRICS/GYNECOLOGY
  * Income Data:
    * Header (prior to csv being read in) and Footer rows needed removal
* Merging & Additional Steps
  * Calculate number of physicians per county
  * Calculate physicians per capita
  * Group population density in equally sized bins
  * Group states by region
  * Define "underserved" as the mean of physicians per capita minus one standard deviation (0.488)
  * Create bins for physicians per capita
* PostgreSQL Database
