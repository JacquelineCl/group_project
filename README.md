# group_project

## Presentation
Selected topic: Primary care physician availability by zip code</n>
Reason why we selected this topic: Because meaningful access to a primary care physician can help reduce health care disparities. </n>This research could be useful for anyone attempting to reduce health care disparities, like universities, businesses, and non-profits to help improve access to a primary care physician in underserved areas. </n>
Description of their source of data: tbd</n>
Questions they hope to answer with the data: Are there are zip codes in the United State that will be underserved or overserved by primary care physicians in xxx years?</n>

## GitHub
Communication Protocols: tbd</n>

## Machine Learning Model

## Database

## Data Sources
(Rev00 Income & Zipcode Data: Tony)[https://www.kaggle.com/hamishgunasekara/average-income-per-zip-code-usa-2018],

(Rev01 Income & Zipcode Data: Jenny)[https://simplemaps.com/data/us-zips],

(Rev 00 Physician & Zipcode Data: Jacqueline)[https://data.cms.gov/provider-data/dataset/mj5m-pzi6],

## References

## Notes
### Jacqueline

### Jenny

### Tony
* The physician data had to be encoded ("ISO-8859-1") in order to work properly
* The number of digits in the zip code ranged from 3-9.  In order to standardize the data, we created functions to either add 1-2 zeroes in front or remove the additional four digits at the end.  In some cases, both were necessary.
* Groupby and Transform were used to create a "doctor_count" column.  This is the total number of doctors per zip.
* Another additional column was added to calculate "doctor_per_pop", but the group should discuss the best method for this column.
