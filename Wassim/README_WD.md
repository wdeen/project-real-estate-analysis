# **Nasdaq-Zillow API: USA Real Estate Data Analysis**

<p align="center">
<img src="./Images/zillow_logo.png" width="750">
</p>

<p align="center">
<img src="./Images/usa_homes.jpeg" width="750">
</p>


## Table of Contents
* [Project Contributors](#project-contributors)
* [Overview](#overview)
* [Effect of Seasonal Changes on Metropolitan Real Estate Inventory (per USA Region)](#effect-of-seasonal-changes-on-metropolitan-real-estate-inventory-per-usa-region)
* [Final Repository Structure](#final-repository-structure)


## Project Contributors
 * **Wassim Deen**
    - [Github] https://github.com/wdeen
  * **Gabriel Adriano**
    - [Github] https://github.com/gadriano11
 * **Jun Leng Tan**
    - [Github] https://github.com/bill-leang


## Overview
For this project, we explored facets of the Nasdaq Zillow API dataset and performed 3 different analyses to unravel interesting trends in the USA real estate market.
Zillow is regarded as the "leading real estate and rental marketplace" with its API built around various market indicators and containing more than 20 years worth of data for "thousands of geographical areas" covering the United States.

For more information: https://data.nasdaq.com/databases/ZILLOW/documentation

Our analyses explore the following topics:
1. Effect of Seasonal Changes on Metropolitan Real Estate Inventory (per USA Region)
2. United States Interest Rates and Property Market Dynamics
3. Median House Prices by City Type in the United States Over Time

In demonstrating our overall data analysis, we each primarily (but not exclusively) used the following Python libraries:
1. **Pandas** - Data Wrangling / Cleaning / Aggregation / Analysis
2. **Matplotlib** - Visualisations of Our Raw / Aggregated Datasets
3. **SciPy** - Various Statistical & Hypothesis Testing


## Effect of Seasonal Changes on Metropolitan Real Estate Inventory (per Metro USA Region)

<p align="center">
  <img src="./Images/usa_census_regions.png" width="45%">
</p>


### **Null Hypothesis (H0):**

There is a statistically significant difference in the For-Sale Inventory across seasons.


### **Alternative Hypothesis (H1):**

There is NO statistically significant difference in the For-Sale Inventory across seasons.


### **ANOVA Test Results:**

#### **USA Northeast Region**

<img src="./Images/Northeast.png" width="100%">

| State Code | State Name        |
| ---------- | ----------------- |
| CT         | Connecticut       |
| MA         | Massachusetts     |
| ME         | Maine             |
| NH         | New Hampshire     |
| NJ         | New Jersey        |
| NY         | New York          |
| PA         | Pennsylvania      |
| RI         | Rhode Island      |
| VT         | Vermont           |

**- F-statistic = 3.946703358362805**
**- p-value = 0.008943123143410924**

**[REJECT Null Hypothesis (H0)]** With 95% confidence, the variability of the For-Sale Inventory in the Northeast Region across seasons is statistically significant.

#### **USA Midwest Region**

<img src="./Images/Midwest.png" width="100%">

| State Code | State Name        |
| ---------- | ----------------- |
| IA         | Iowa              |
| IL         | Illinois          |
| IN         | Indiana           |
| KS         | Kansas            |
| MI         | Michigan          |
| MN         | Minnesota         |
| MO         | Missouri          |
| ND         | North Dakota      |
| NE         | Nebraska          |
| OH         | Ohio              |
| SD         | South Dakota      |
| WI         | Wisconsin         |

**- F-statistic = 5.875017566328791**
**- p-value = 0.0006887615533247862**

**[REJECT Null Hypothesis (H0)]** With 95% confidence, the variability of the For-Sale Inventory in the Midwest Region across seasons is statistically significant.

#### **USA South Region**

<img src="./Images/South.png" width="100%">

| State Code | State Name           |
| ---------- | -------------------- |
| AL         | Alabama              |
| AR         | Arkansas             |
| DC         | Washington, D.C.     |
| DE         | Delaware             |
| FL         | Florida              |
| GA         | Georgia              |
| KY         | Kentucky             |
| LA         | Louisiana            |
| MD         | Maryland             |
| MS         | Mississippi          |
| NC         | North Carolina       |
| OK         | Oklahoma             |
| SC         | South Carolina       |
| TN         | Tennessee            |
| TX         | Texas                |
| VA         | Virginia             |
| WV         | West Virginia        |

**- F-statistic = 1.3639286436735938**
**- p-value = 0.2543987237874858**

**[FAILED TO REJECT Null Hypothesis (H0)]** At 5% risk level, the variability of the For-Sale Inventory in the South Region across seasons is NOT statistically significant.

#### **USA West Region**

<img src="./Images/West.png" width="100%">

| State Code | State Name       |
| ---------- | ---------------- |
| AK         | Alaska           |
| AZ         | Arizona          |
| CA         | California       |
| CO         | Colorado         |
| HI         | Hawaii           |
| ID         | Idaho            |
| MT         | Montana          |
| NM         | New Mexico       |
| NV         | Nevada           |
| OR         | Oregon           |
| UT         | Utah             |
| WA         | Washington       |
| WY         | Wyoming          |

**- F-statistic = 9.395782823063112**
**- p-value = 6.692988590780285e-06**

**[REJECT Null Hypothesis (H0)]** With 95% confidence, the variability of the For-Sale Inventory in the West Region across seasons is statistically significant.


## Final Repository Structure
