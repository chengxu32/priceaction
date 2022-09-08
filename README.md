## Performing price action analysis with FinSpace

This repository contains sample notebook that uses FinSpace to back test price action trading pattern "[Head and Shoulders](https://www.investopedia.com/terms/h/head-shoulders.asp)", which is refeered as HS.

### Price action workflow

The [price action notebook](price-action.ipynb) shows the workflow of loading trade and quote data and identifying price action patterns.
It covers the following steps:  
1.	Load raw security price data into FinSpace for further processing and analysis. 
2.	Select the desired trading frequency
3.	Prepare data for the pattern identification algorithm/model
4.	Run the algorithm/model to identify the price action patterns
5.	Plot the pattern on the price chart for verification

![Image](price-action-workflow.png)


### FinSpace workflow

Steps belows show how to run the Jupyter notebook in managed Amazon FinSpace Spark cluster to perform price action analysis on HS pattern:

1.	Load “US Equity TAQ - AMZN 6 Months” data that is provided as part of the Capital Markets Sample Data Bundle installed in the Amazon FinSpace environment by default. 
2.	Aggregate the price data at various lower frequencies and identify the ones for which the price action patterns are pronounced and tradable.  
3.	Further aggregate the data to the desired frequency by calling FinSpace time bar collection, summarization and filling and filtering functions.
4.  Smooth the resultant price series using functions provided in FinSpace analytical library (e.g. Exponential Moving Average)  
4.	Find all the local minima and maxima of the smoothed price series, then identify both HS and Inverse HS (IHS) patterns 
5.	Plot all the identified HS and IHS patterns in the price series chart.

![Image](head-and-shoulder.png).


## Conclusion

This notebook demonstrates how to perform Price Action Analysis using FinSpace and PySpark. You can use it as a foundation to back test price action trading patterns of your interest.
