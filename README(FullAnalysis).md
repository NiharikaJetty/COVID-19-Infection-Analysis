# COVID-19 Infection Analysis
This project utilizes R Studio to perform an analysis on a global COVID-19 infection dataset from 2020

## INTRODUCTION
According to Johns Hopkins Medicine (https://www.hopkinsmedicine.org/health/conditions-and-diseases/coronavirus), COVID-19 is a viral disease caused by the SARS-CoV-2 Virus. After emerging in early December of 2019, Coronavirus caused a global pandemic, taking the lives of millions around the world. After the very first case was reported on December 1st, 2019 in Wuhan, China, there has been a plethora of available data on the spread, infection rate, death rate, and so on. From January to December of 2020, there have been around 1.8 million deaths globally, with many more unreported and/or undiagnsoed. In this project, I performed a statistical analysis on global COVID-19 data collected from 2020. For more information on COVID-19, please visit the Center of Disease Control (CDC) website: https://www.cdc.gov/coronavirus/2019-ncov/index.html

### PREPARATION & INITIAL INSIGHTS

#### DATA INTEGRITY
Upon loading and preparing data in R, I noticed some potential issues to keep in mind. The "death" column had to be cleaned, since there were too many distinct variables. A "0" value represented no death, whereas a "1" value meant death, but certain values were inputed as dates, therefore the data needed to be standardized. However, for the recovery column, it is unclear whether a "0" value represents a successful or unsuccesfull recovery of a patient. Attempts to determine this by comparing it to death values failed as the values were not consistent. Furthermore, other variables such as "case in country" and "x" are missing more than 1/3 of their values altogether. This is something to keep in mind while evaluating the integrity of this data set.

I observed the following trends after applying statistical principles and Welch Two-Sample T. Tests to determine statistical significance:
- Total death rate is 5.806%
- Recovery rate is 14.654%

DEATH:
- Average age of dead person is 68.5 years
- Youngest age who died is 36 years
- Oldest age who died is 89 years

ALIVE:
- Average age of survivor is 48.1 years
- Youngest survivor is 4 months old
- Oldest survivor is 96 years
