# Zillow Time Series Forecasting Project

By: Alexis Kedo

This project uses the average sale price for residential properties in individual U.S. zipcodes to forecast the 3-year return on investment (ROI) for a select group of zipcodes in three population density categories: urban/densely populated, mid-size, and rural/sparsely populated.  
## Business Understanding 
For this project, my hypothetical client was a start-up, OpenDoor, whose profits are based on flipping and selling residential properties for which they make instant cash offers. They are currently operating in 27 markets across the United States and are looking to capitalize on the current spike in demand for housing. They would like to know the top 5 most promising zip codes to invest in in 2021.

I integrated population data into my dataset and split the data into three groups: urban, mid-size, and sparsely populated/small. 
## Data Understanding
The data used for this analysis comes from Zillow and was provided by [Flatiron School](https://github.com/learn-co-curriculum/dsc-phase-4-project/blob/main/time-series/zillow_data.csv). I also used population data from the [2010 U.S. Census](https://catalog.data.gov/dataset/2010-census-populations-by-zip-code). 

The data includes average home sale prices by month for 14,723 zipcodes from April 1996 to April 2018, though I predicted on the timeframe of June 2009 to April 2018. 
## Methods 
I isolated, according to descriptive statistics, the top 10 zipcodes for each population density category, and then chose a representative zipcode on which to optimize a SARIMA model. I improved my model through a combination of auto-ARIMA gridsearches and manully selecting hyperparameters, based on my knowledge of the seasonality present in the dataset. Then, I ran all 30 zipcodes through the final model to find the zipcodes with the largest 3-year predicted return on investment.
## Results 
On the whole, mid-size and small-size zipcodes are projected to have less risky investment potential than urban, densely-populated zipcodes. In fact, many urban zipcodes are projected to lose values in the next three years: 
![matrix](https://github.com/alexiskedo/zilloracle/blob/main/images/urban_results.png)
One of the zipcodes, in Bellevue, Washington (98105) is projected to deliver somewhat immediate gratification, with a projected three-year ROI of 169%: 
![matrix](https://github.com/alexiskedo/zilloracle/blob/main/images/midsize_results.png)
Lastly, many sparsely populated zipcodes also look promising, namely Massachusetts (02111), with a project three-year ROI of 49%: 
![matrix](https://github.com/alexiskedo/zilloracle/blob/main/images/rural_results.png)
## Recommendations, Evaluation and Next Steps 
Recommended zipcodes for investment are as follows: 
   1. **Bellevue, WA** (98105)
       169% Predicted 3-Year ROI
   2. **Boston, MA** (02111)
       49% Predicted 3-Year ROI 
   3. **Haworth, OK** (74740)
       6.24% Predicted 3-Year ROI 
   4. **Moss Beach, CA** (94038) 
       4.27% Predicted 3-Year ROI 
   5. **Hertford, NC** (27980)
       3.74% Predicted 3-Year ROI 

My optimized model has a not-insignifcant error of +/- 30% ROI. Given more time, I would manually tune the seasonal hyperparameters in my SARIMA model to further reduce this error. Further, the datasets could be updated to include more accurate, 2020 Census data. 
## Repository Structure
```
├── images
├── Notebook (Real_Estate_Time_Series_Analysis).ipynb
└── README.md
├── Presentation (Zillow_Time_Series_Forecasting_Project.pdf)

```