# Health Care Disparities - Primary Care Access Analysis

## Overview
* Selected topic:
  * Health Care Disparities - Primary Care Access Analysis
* Reason for selecting this topic:
  * Because meaningful access to a primary care physician can help reduce health care disparities. This research could be useful for anyone attempting to reduce health care disparities, like universities, businesses, and non-profits to help improve access to a primary care physician in underserved areas.
* Description of data sources listed below
* Questions to answer with the data:
  * Are there are counties in the United State that will be underserved by primary care providers in the United States?
  * Are there any other factors that impact availability, like income, region, or population?

## Conceptual ERD

![image](https://user-images.githubusercontent.com/67409852/154579881-44d03c5b-2a0f-42bb-b6e0-8a4b2d622aa2.png)

## Database
PostgreSQL 11

![image](https://user-images.githubusercontent.com/67409852/154578261-ae821af4-9000-4e11-ae76-958689a9ca9c.png)

## Merged DataFrame from PostgreSQL

![image](https://user-images.githubusercontent.com/67409852/154594548-06c1c284-1284-492b-a761-c2453bea59d5.png)

## Machine Learning Model
* Supervised Machine Learning: Logistical Regression
  * We have a question we want to answer, therefore, supervised machine learning is the appropriate choice for this analysis. Logistical Regression will separate the data into two categories, counties that will be underserved by primary care physicians, and counties that will be appropriately served by primary care physicians.
* Accuracy score: 89.6%
* R-squared score: 58.3%

![image](https://user-images.githubusercontent.com/67409852/154203477-0df29c6d-59cb-444a-8c9a-96c99ec7fb56.png)

### After Hyper Tuning (stratifying data and increasing estimators from 100 to 200)
* Accuracy score: 91.8%
* R-squared score: 67.3%

![image](https://user-images.githubusercontent.com/67409852/154868594-716fba52-3934-4a83-b045-e88bb85310ef.png)

## Data Sources
Income: [https://apps.bea.gov/iTable/iTable.cfm?reqid=70&step=30&isuri=1&major_area=4&area=xx&year=2020&tableid=20&category=720&area_type=4&year_end=-1&classification=non-industry&state=xx&statistic=3&yearbegin=-1&unit_of_measure=levels],

Population: [https://covid19.census.gov/datasets/average-household-size-and-population-density-county/explore?location=18.793911%2C0.315550%2C3.67&showTable=true],

Zip Codes: [https://simplemaps.com/data/us-zips],

Physician: [https://data.cms.gov/provider-data/dataset/mj5m-pzi6],

Regions: [https://www.bea.gov/news/2015/gross-domestic-product-state-advance-2014-and-revised-1997-2013/regional-maps],

Regions: [https://www.businessinsider.com/regions-of-united-states-2018-5#lastly-the-petroleum-administration-for-defense-uses-this-map-of-five-regions-originally-drawn-up-in-1942-to-ration-the-countrys-gasoline-10],

## Analysis Results and Summary
Disparities in healthcare are an every day reality in the United States so identifying ares for improvement is crucial for the health and well-being of communities. To answer the question "Are there are counties in the United States that will be underserved by primary care providers in the United States?", a supervised machine learning model is the most appropriate choice. Our model, with an accuracy score of 91.8%, the amount of primary care physicians per capita. With a r2 score of 67.3%, the model will predict new data points around 70% of the time, showing the model is not prone to overfitting. 

According to the data, any county with 0.488 primary care physicians per capita or less is "underserved". Out of 3,092 counties, 148 are underserved, or around 5% of all counties, while 2881 counties, or ~95% of counties are appropriately served.

![image](https://user-images.githubusercontent.com/67409852/155261745-376a9a31-1e1e-4a56-a54e-3296e236bb6c.png)

![image](https://user-images.githubusercontent.com/67409852/155261513-a3b704ee-9511-422c-8186-f2e94538c9d2.png)

## References

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
