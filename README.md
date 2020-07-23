# startup_investments_exploration


| Language | Type          | Date  | Due | Author               |
| -------- | ------------- | ----- | ---- | -------------------- |
| Python   | GA Final Project  | 7/16/2020 | 7/23/2020 | Adam Mayorca |


## Overview

The Startup Investments Exploration project is an exploratory data science project that explores and analyzes the given data set, formulates hypotheses, and provides insights.



## The Data Set
This data set has startup investment data, capturing detailed information around the company funding rounds, their status, and post-IPO (initial public offering) figures - if applicable. The data set includes, but is not limited to, categorizations by market/industry, country and state (if US based). 

The data appears to come from Crunchbase and was retreived from [Kaggle](https://www.kaggle.com/arindam235/startup-investments-crunchbase). The data set may be downloaded from this repo, but is also accesible on Kaggle's website. A user account may be required to access the data on their site. 

As of 7/16/2020, the data set has 54,294 rows and 39 columns.



### Code Snipets
Sample function that takes a data frame and creates a pie chart that breaks down the company statuses for that data frame. 


```python
def print_status_pie(market_df):
    # This function will print out a pie chart broken down by status for
    # the provided data frame. Data frame must have a status column
    
    operating_mask = market_df['status'] == 'operating'
    acquired_mask = market_df['status'] == 'acquired'
    closed_mask = market_df['status'] == 'closed'
    
    operating_count = len(market_df[operating_mask])
    acquired_count = len(market_df[acquired_mask])
    closed_count = len(market_df[closed_mask])
    
    status_df = pd.DataFrame({'status':[operating_count, acquired_count, closed_count]},
                            index=['operating','acquired','closed'])
    
    plot = status_df.plot.pie(y='status', figsize=(5, 5), autopct='%1.0f%%')
    
    print("Total number of companies: ", len(market_df))
    print("--------\n")

```

## Conculsions

Conclusions are captured in the Notebook.

