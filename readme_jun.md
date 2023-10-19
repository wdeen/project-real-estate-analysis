# Median House Price Change In Various Cities Over Time









## Guidelines on Jupyter notebook code (Jun Leng Tan section, third section)

1. Run all of the cells sequentially in Jupyter Notebook to ensure that all dataframes and visualizations are created.

2. Each visualization is generally followed by an explanation or analysis, sometimes the write-up is in the next figure as they are compared together.

   
## About the datasets used: sssm_combine, srsm_combine, issm, irsm
  ### sssm_combine
  - It contains smoothed data metropolitan area monthly median house price over the years ( in each state as well as the whole of US (region = 'United States') (90705 rows x 8 columns)  joined with the region info (a table of 89,305 rows by 3 columns).
  - The date range may defer from city to city.   
  - Different states have different numbers of metro area (AK, Alaska, only has 1, CA, california, has 34.  
  - The difference between smoothed and raw data on Zillow is that the former removes 'spikes' in the raw data to make the chart look 'smoother', which is fine for our purpose. Data wise, the smoothed data will have their tail components adjusted to give the graph a "smoother" appearance, otherwise the raw data may have many "steps" or small flat lines. (e.g 130,750 (smooth) vs 130,000 (raw)). According to Zillow, the adjustment may also be for seasonal reason.  
      - The raw data also have slightly more data points than the smoothed data (93075 vs 92558, 0.56% less).  
      - Raw data also has State typo (eg. "NC; NC"), which may be introduced during data input.
  ### srsm_combine
  - It is the counterpart of sssm_combine but with raw data
  ### issm
  For-Sale Inventory (number of listings) (Smooth, SFR only, Monthly) (61919 rows × 4 columns)
  ### irsm
  For-Sale Inventory (number of listings) (Raw, SFR only, Monthly) (61919 rows × 4 columns)

## Finding on Smooth vs Raw data sets  
- The raw data has more spikes compared to the smooth data (thus the name 'smooth')
- As expected the correlation also dropped slightly (0.95 for smooth to 0.93 for raw)

<p align="center">
  <img alt="smooth data" src="./Images/dayton_us_smooth.png" width="45%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="raw data" src="./Images/dayton_us_raw.png" width="45%">
</p>


## Finding on linear regression for smooth vs raw
- From the graph we can see that there is generally a negative correlation between the house price and number of listing. This makes sense from a supply-demand perspective. As the more supply (listing) there is, the lower the price will be given the same demand. The r-squared value is significant, meaning the regression model is quite reliable.  
    - Comparing the smooth to raw, the smooth data has higher r-squred value (0.43 vs 0.26), meaning the linear regression model using smoothed data is more predictable, because the data seems to have been 'compacted' during the smoothing process as we can see the data points are closer together to the regression line in the smooth dataset.

<p align="center">
  <img alt="smooth scatter plot" src="./Images/scatter_smooth.png" width="45%">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="raw scatter plot" src="./Images/scatter_raw.png" width="45%">
</p>

## Explanation  
  The locations of the cities that we have chosen as the representation of the 3 city sizes (big, medium, small). The size of the dot indicates the median house price in each city.
<p align="center">
  <img alt="cities" src="./Images/3citiesOnMap.png" width="45%">
&nbsp; &nbsp; &nbsp; &nbsp;
</p>

## Finding on different sized cities compared to national house price trend
- As expected the big city has the highest price, followed by medium and finally the small city.
- One would expect the big city to have a higher correlation with national price than the smaller ones, because they have a bigger weight when compared to the smaller cities in the calculation of the national price, but it turned out that Killeen (a medium city) has the highest correlation (0.982) vs big city New York's 0.957 and small city Davenport's 0.911. This could be because the national price is a median price which is closest to the medium sized city's price (50th percentile price). As it can be reasonably assumed that when ranked by price, the bigger the city the higher its median price.
- House prices dropped across the country in 2008 because of the Great Financial Crisis (GFC), during which the big city price was impacted the most, while the smaller cities were affected the least. It took NY ten years (2018) to recover the drop in price during the GFC.
- Similar to Australia, the house prices in the US continue to price even more markedly during the pandemic (orange part of the graph)
<p align="center">
  <img alt="cities" src="./Images/citiesMedianHsePriceTrends.png" width="45%">
&nbsp; &nbsp; &nbsp; &nbsp;
</p><p align="center">
  <img alt="covid effect" src="./Images/corr_withNationalTrend.png" width="45%">
</p>
## A brief analysis of house prices before and during covid  
  - It appears that although the pandemic does not affect the cycle of the house price much (still around 1 year), it does amaplify the magnitude of the cycle (there is a bigger difference between the trough and crest of the cycle).  
  - It also appears during covid the price seems less stable as there is more volatility as seen from multiple mini-cycles towards the beginning of 2022.
<p align="center">
  <img alt="covid effect" src="./Images/beforeAndAfterCovid.png" width="45%">
</p>



 
