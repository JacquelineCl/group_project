# Health Care Disparities - Primary Care Access Analysis

## Presentation
* Selected topic:
  * Health Care Disparities - Primary Care Access Analysis
* Reason for selecting this topic:
  * Because meaningful access to a primary care physician can help reduce health care disparities. This research could be useful for anyone attempting to reduce health care disparities, like universities, businesses, and non-profits to help improve access to a primary care physician in underserved areas.
* Description of data sources listed below
* Questions to answer with the data:
  * Are there are counties in the United State that will be underserved (less than 5 per population) by primary care providers in the United States?
  * Are there any other factors that impact availability, like income, region, or population?

## GitHub
* Communication Protocols: Communicate via Slack and meet in person when needed

## Conceptual ERD

![image](https://user-images.githubusercontent.com/67409852/153738605-b5d3416a-2c71-4bd6-91fa-a41d292e1062.png)

## Database
PostgreSQL 11

![image](https://user-images.githubusercontent.com/67409852/153801216-8b1cbe25-ceef-4d1d-bac6-87559d2091e9.png)

![image](https://user-images.githubusercontent.com/67409852/153800801-c78f952b-5490-446e-b5b3-cef312343e26.png)

## Machine Learning Model
* Supervised Machine Learning: Logistical Regression
  * We have a question we want to answer, therefore, supervised machine learning is the appropriate choice for this analysis. Logistical Regression will separate the data into two categories, zip codes that will be underserved by primary care physicians, and zip codes that will be overserved by primary care physicians.

## Data Sources
(Income)[https://apps.bea.gov/iTable/iTable.cfm?reqid=70&step=30&isuri=1&major_area=4&area=xx&year=2020&tableid=20&category=720&area_type=4&year_end=-1&classification=non-industry&state=xx&statistic=3&yearbegin=-1&unit_of_measure=levels],

(Population)[https://covid19.census.gov/datasets/average-household-size-and-population-density-county/explore?location=18.793911%2C0.315550%2C3.67&showTable=true],

(Zip Codes)[https://simplemaps.com/data/us-zips],

(Physician)[https://data.cms.gov/provider-data/dataset/mj5m-pzi6],

(Regions)[https://www.bea.gov/news/2015/gross-domestic-product-state-advance-2014-and-revised-1997-2013/regional-maps],

(Regions)[https://www.businessinsider.com/regions-of-united-states-2018-5#lastly-the-petroleum-administration-for-defense-uses-this-map-of-five-regions-originally-drawn-up-in-1942-to-ration-the-countrys-gasoline-10],

## References

## Notes
### Jacqueline
* The API section of the physicians website was not working. Emailed website support for resolution. Exploring alternate options for loading the data. Decided to use the downloadable file. 
* Population density vs Urban/Rural categories.
* Machine Learning Model

### Jenny
* Database Markup
* Database choice
* Income and ZCTA data
* ZCTA Data Cleaning
* Machine Learning Model

### Tony
* Sources for Income & Population
* Data Cleaning & Merging:
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
  * Income Data:
    * Header (prior to csv being read in) and Footer rows needed removal
