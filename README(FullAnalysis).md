# COVID-19 Infection Analysis

This project utilizes R studio to perform a statistical analysis on Covid-19 infection data. The analysis is performed on an international dataset from 2020.

**INTRODUCTION**

According to Johns Hopkins Medicine ([https://www.hopkinsmedicine.org/health/conditions-and-diseases/coronavirus](https://www.hopkinsmedicine.org/health/conditions-and-diseases/coronavirus)), COVID-19 is a viral disease caused by the SARS-CoV-2 Virus. After emerging in early December of 2019, Coronavirus caused a global pandemic, taking the lives of millions around the world. COVID-19 is mainly a respiratory illness, however its severity compromises the immune system, making victims more susceptible to other ailments, proving fatal.  In this project, I performed a statistical analysis on global COVID-19 data collected from 2020. For more information on COVID-19, please visit the Center of Disease Control (CDC) website: [https://www.cdc.gov/coronavirus/2019-ncov/index.html](https://www.cdc.gov/coronavirus/2019-ncov/index.html)

**WHY IS THIS IMPORTANT?**

After the very first case was reported on December 1st, 2019 in Wuhan, China, there has been a plethora of available data on the spread, infection rate, death rate, and so on. From January to December of 2020, there have been around 1.8 million deaths globally, with many more unreported and/or undiagnosed. The rapid spread of the disease and mass deaths have caused mass hysteria leading to fear mongering, false information on the virus, and severe racial criticism across the globe. Furthermore, one of the biggest questions that was asked was why this wasn’t predicted previously, and what can we do to prepare for similar situations in the future. The importance of analyzing past data lies in the future; if we can determine trends and analyze relationships from the past, we can use it to help us predict future outbreaks, and prepare us if so. 

**DATA INTEGRITY**

The dataset used in this analysis is from 2021, therefore, a year outdated. However, I believed this was still ideal for analysis since the author updates its validity daily. This can give us accurate insights into using past trends and help us to predict future ones. The dataset can be accessed on Kaggle with this link: [https://www.kaggle.com/datasets/sudalairajkumar/novel-corona-virus-2019-dataset](https://www.kaggle.com/datasets/sudalairajkumar/novel-corona-virus-2019-dataset)

Thanks to John Hopkins University the data set used in this study is a modified version of the below data - - [https://docs.google.com/spreadsheets/d/1yZv9w9zRKwrGTaRYzmAqMefw4wMlaXocejdxZaTs6w/htmlview?usp=sharing&sle=true](https://docs.google.com/spreadsheets/d/1yZv9w9zRKwrGTaR-YzmAqMefw4wMlaXocejdxZaTs6w/htmlview?usp=sharing&sle=true)

#### ABOUT THE DATA SET

There are 1087 observed values with 27 measured variables within this set. Below are the following descriptors that I will use in my analysis:

- Sno - Serial number
- ObservationDate - Date of the observation in MM/DD/YYYY
- Province/State - Province or state of the observation (Could be empty when missing)
- Country/Region - Country of observation
- Last Update - Time in UTC at which the row is updated for the given province or country.
- Confirmed - Cumulative number of confirmed cases till that date
- Deaths - Cumulative number of of deaths till that date
- Recovered - Cumulative number of recovered cases till that date

Upon loading and preparing data in R, I noticed some potential issues to keep in mind. The "death" column had to be cleaned, since there were too many distinct variables. A "0" value represented no death, whereas a "1" value meant death, but certain values were inputed as dates, therefore the data needed to be standardized. However, for the recovery column, it is unclear whether a "0" value represents a successful or unsuccessful recovery of a patient. Attempts to determine this by comparing it to death values failed as the values were not consistent.

Other variables such as "case in country" and "x" are missing more than 1/3 of their values altogether. This is something to keep in mind while evaluating the integrity of this data set. The “Last Update” values are not standardized, so this had to be cleaned as well. 

### ANALYSIS

I observed the following trends after applying statistical principles and Welch Two-Sample T. Tests to determine statistical significance:

- Total infected countries: 223
- Total Recovered cases: 24,996,456 people
- Total Deaths: 84,299 people
- Total Confirmed Cases: 16,409,757 people
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

With millions dying from COVID-19, there were many arguments regarding whether the average age of those who die from this virus is higher than the age of those who survive. After conducting the Welch 2-Sample T-Test (99% confidence interval), I got the following values:  t = -10.839, df = 72.234, p-value < 2.2e-16

- Since the p-value is < 0.05, we reject the null hypothesis. This test proves that there is a statistical significance in the argument that the average age of survivors is younger than that of the dead.

Active Cases = Number of Confirmed Cases - Number of Recovered Cases - Number of Death Cases

Increase in number of Active Cases is probably an indication of Recovered case or Death case number is dropping in comparison to number of Confirmed Cases drastically. Will look for the conclusive evidence for the same in the notebook ahead.

Percentage of all Types of Cases
![Pie of Case Types](https://user-images.githubusercontent.com/71042140/200218794-965caf79-7de2-48bf-b348-2ab1a3c13a8b.png)

Distribution of Age across study
![file_show (1)](https://user-images.githubusercontent.com/71042140/200218873-233643c4-74a8-4c9b-abc4-be939930d30d.png)


[https://www.kaggle.com/code/abhinand05/covid-19-digging-a-bit-deeper](https://www.kaggle.com/code/abhinand05/covid-19-digging-a-bit-deeper)
