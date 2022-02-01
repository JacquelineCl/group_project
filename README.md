# group_project

## Presentation
* Selected topic:
  * Primary care physician availability by zip code
* Reason for selecting this topic:
  * Because meaningful access to a primary care physician can help reduce health care disparities. This research could be useful for anyone attempting to reduce health care disparities, like universities, businesses, and non-profits to help improve access to a primary care physician in underserved areas.
* Description of data source:
  * TBD
* Questions to answer with the data:
  * Are there are zip codes in the United State that will be underserved or overserved by primary care physicians in xxx years?

## GitHub
Communication Protocols: tbd</n>

## Machine Learning Model
Supervised Machine Learning: Logistical Regression
We have a question we want to answer, therefore, supervised machine learning is the appropriate choice for this analysis. Logistical Regression will separate the data into two categories, zip codes that will be underserved by primary care physicians, and zip codes that will be overserved by primary care physicians.

## Database
PostgreSQL 14

## Data Sources
(Rev00 Income & Zipcode Data: Tony)[https://www.kaggle.com/hamishgunasekara/average-income-per-zip-code-usa-2018],

(Rev01 Income & ZCTA Data: Jenny)[https://simplemaps.com/data/us-zips],

(Rev 00 Physician & Zipcode Data: Jacqueline)[https://data.cms.gov/provider-data/dataset/mj5m-pzi6],

## References

## Notes
### Jacqueline

### Jenny
* Database Markup
* Database choice
* Income and ZCTA data
* ZCTA Data Cleaning
* Machine Learning Model

### Tony
* The physician data had to be encoded ("ISO-8859-1") in order to work properly
* The number of digits in the zip code ranged from 3-9.  In order to standardize the data, we created functions to either add 1-2 zeroes in front or remove the additional four digits at the end.  In some cases, both were necessary.
* Groupby and Transform were used to create a "doctor_count" column.  This is the total number of doctors per zip.
* Another additional column was added to calculate "doctor_per_pop", but the group should discuss the best method for this column.
