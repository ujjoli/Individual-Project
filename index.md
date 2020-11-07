
# Income, Inflation, Expenditure Analysis by US States

Welcome all !! The purpose of this analysis is to see how US, states of US is doing with it GDP, income and expenditure. This analysis finds some insights about inflation, spending behavior of states and residents. 

*_P.S:_* the data needed for this project is taken from **[BEA's Website](https://apps.bea.gov/regional/downloadzip.cfm)**. Also, while computing the filter and analysis 
for this project, I have compared 50 states and Disctrict of Colombia (DC)

As expected, to accomplish the analysis, I have gone through several steps:

## 1. Importing packages
While importing packages, I have imported many library and packages with it. Sample of my code is:
```
import pandas as pd

#pip install jupyter_plotly_dash

import zipfile
import matplotlib
matplotlib.style.use('ggplot')
import plotly
import plotly.offline as pyo              #with this I will be able to plot charts offline
import plotly.graph_objects as go            #using plotly graph objects
import dash                                 #enables to build interactive web based applications (charts, graphs)
from jupyter_plotly_dash import JupyterDash   #enables to run dash from jupyter
import dash_core_components as dcc            # to create graph in our layout 
import dash_html_components as html            # to generate html components and use them
from dash.dependencies import Input, Output      #to make the dash apps interactive

from IPython.display import display
plotly.offline.init_notebook_mode()
```
For full length of my code, click here

## 2. Importing files and Reading
I downloaded the zipfiles from BEA's website. I downloaded 9 of them each of around 50000 rows and 30 columns.
Sample of my code is:
```
def extract_zipfile(file):                        
    with zipfile.ZipFile(file,'r') as zip_r:
        zip_r.extractall()
    extract = zip_r.namelist()
    return extract
    
    file='SAINC Annual Personal Income and Employment By State.zip'
    zip_read_api = extract_zipfile(file)
  ```
 For full length of my code, click here
## 3. Filtering data and Processing
To come up with specific insights, visualization, filtering and processing of datasets is necessary, so many times I used dropping, accessing specific rows and columns, iterating over list, columns and rows, performing some calculations and even sometime creating a new data frame from the data I have.
Some sample of my code is:

```
income_state_employment_df_all=income_state_employment_df_all.dropna()
----------------------------------

def filter(x):
    x_drop = x.drop(['GeoFIPS','Region','Unit','TableName','LineCode',
                                                               'IndustryClassification'], axis=1)
    years =  x_drop.iloc[:,2:13]
    x_filter= x_drop.drop(years, axis=1)
    x_filter =x_filter.rename(columns={"GeoName":"States"})
    
    return x_filter  
  (Note: This is just sample.)
```
For full length of my code, click here
## 4. Visualization and Analysis
  
  For ease of visualization and analysis, I have divided the analysis part into 5 categories:
  1. [Analysis of GDP](https://github.com/ujjoli/Individual-Project/blob/gh-pages/GDP.md)
  2. [Aanalysis of Income](https://github.com/ujjoli/Individual-Project/blob/gh-pages/Income.md)
  3. [Analysis of Personal expenditure and Inflation](https://github.com/ujjoli/Individual-Project/blob/gh-pages/Expenditure.md)
  4. Analysis of Relative Cost and living
  5. Co-relation between GDP and Relative Cost and living
  
 # Findings and Conclusions
 
 * From all the analysis and visualizations, it was interesting to find that California has the highest GDP in 2019 and it's GDP major contribution comes 
 from Real estate, rental and leasing area with 40.0% .This can indicate that businesses related to real estate must be in good position and there might be a 
 good chance that many people are employed in Real estate, rental and leasing in California.
 
 * We also came to know that over time the personal income has been increasing in all states and people are being able to bring more paycheck home in 2019 
 than in 2009. If we come for recent year (2019), CA has highest personal income, comparably with other states. While comparing the personal income in 
 different areas like wages and salaries, manufacturing, transportation, government enterprises and so on, we can find the common pattern that California 
 dominates all of the states in different areas. 
 
 * Moving on, the analysis of spending pattern is significant as it point out towards the inflation and as well as consumer spending pattern. While comparing
 spending pattern to income,it tells us out if people are able to save some money. Per capita expenditure is increasing in same pattern like the per 
 capita income. From 2008 to 2018 and more, both per capita income and expenditure are increasing with same slope. This means that the amount of per person
 spending has been significantly increased. However, because of the parallel increase in per capita income, there does not seem to be adverse effect. 
 And the gap between these lines are showing that each person have been saving some amount of money. This can help the policy makers to control the market 
 price accordingly. I would like to see which state has increased their spending rate and by how much from 2008 to 2019. California people have increased 
 their spending rate by 40%. In same way, even other states people are not that far away. This can lead to a point that though inflation have surged 
 abundantly, increase in each person's people income in all these states have maintaine that difference. 
 
 * It also was known that Housing and utilities, health care and financial services and insurance are top priorities for all state residents to spend their 
 dollars. That is why affordable health care and affordable health care is always the biggest question. we came to know that housing and utility seem to be
 top priority of many residents. Hawaii, California , Massachussets, DC and New York have highest RPP indicating they are the moest expensive place to live.
 It is interesting that California has the highest spending rate, more contributed by housing and rental utility, seems to have similar pattern with RPP. 
 We can be convinced that, if we get job offer from California and Alaska with equal salaries and benefits (assuming all other facilites to be similar) and 
 want cheaper place to live in, we have to go with job offer from Alaska and Alabama.

* Finally, I would like to see if increase in GDP of that state will increase RPP of that state. Though California, Hawaii's GDP had positive realtion 
with their RPP, just the GDP of state might not be enough to co-relate with state's RPP. There might be other factors they come in play.


  


