# The Amazon Rainforest: Is Deforestation Increasing?

Author: Vijay Kumar

## Project Overview

The Amazon rainforest is disappearing at an alarming rate in Brazil. Each year thousands of kilometers of rainforest are destroyed from deforestation. The Amazon rainforest is the world's biggest rainforest. The Amazon rainforest offers a huge ecosystem containing about 30 percent of the world's species and sustaining life for people, animals, and plants across many Brazilian states. What happens when the developing environment in this area of the world is destroyed? What massive repercussions could there be for the world? How do many aspects of life such as the conquests of forest fires, the configurations of weather phenomena, the growth of population, and the expansion of GDP influence the deforestation of the Amazon? Will the Amazon rainforest still exist in years to come if deforestation continues? 


## The Data

The data for my project was on topics that could relate to the Amazon rainforest. 

I compiled three Kaggle datasets for my project from https://www.kaggle.com/mbogernetto/brazilian-amazon-rainforest-degradation. The first Kaggle dataset on Amazon deforestation was originally sourced from The Brazilian Amazon Rainforest Monitoring Program by Satellite. The dataset contains 16 rows and 11 columns. The second Kaggle dataset about fire outbreaks came from The Fires Database at The National Institute for Space Research. The dataset holds 2104 rows and 6 columns. The third Kaggle dataset on weather phenomena was initially derived from Golden Gate Weather Services. The dataset has 16 rows and 5 columns.

I obtained additional data of Brazilian population statistics from https://www.macrotrends.net/countries/BRA/brazil/population. 

I used data of Brazil GDP statistics from The World Bank Group at https://data.worldbank.org/indicator/NY.GDP.PCAP.CD?end=2019&locations=BR&start=1960&view=chart.

All data I included occurred between the years 1999 and 2019.

## Data Preparation

In order to start to distinguish if Amazon deforestation is increasing, I created a plot of the total deforestated area across all Brazilian states in the Amazon for each year between 2004-2019. The plot is given in the images file.

Deforestation generally decreased from 2004-2012, but then increased in more current time of 2012-2019. 

I desired to identify how Amazon deforestation totals associate with each Brazilian state, weather phenomena, forest fires, population, and GDP(US dollars). I constructed a variety of plots and graphs to look at each of the mentioned features in relation to Amazon deforestation totals between 1999-2019.

Weather phenomena was found to have little correlation with Amazon deforestation between 1999-2019 (see Amazon.ipynb for further details) so I did not include this element for analysis when I went on to further analysis and modeling. Overall, there was a lack of a strong relationship between weather phenomena and Amazonian deforestation, which suggests more human causes of deforestation than natural causes.

I created a dataset to look at the correlations of the other deforestation-related features in comparison with Amazon deforestation as a whole. My plot of the correlations in the images file.

The deforestation amounts for the Brazilian states of Mato Grosso, Para, and Rondonia were the most correlated with total Amazon deforestation amounts across all states.  These states are fairly large states so holding high correlation percentages with total Amazonian deforestation is not unusual. Firespots were about 83% correlated with the total Amazon deforestation suggesting a strong relationship between fire outbreaks and Amazonian deforestation. Fire outbreaks may lead to deforestation. Population and GDP per capita(US dollars) had strong inverse correlations with total deforestation. Population was about 71% inversely correlated with total Amazon deforestation and GDP per capita(US dollars) was about 86% inversely correlated with total Amazon deforestation. Population decreasing with more Amazon deforestation sadly makes sense. GDP per capita(US dollars) decreasing with increasing deforestation of the Amazon could be concerning.

I used the correlation plotted features that relate to Amazon deforestation when I went on to modeling. 

## Data Modeling

### Modeling 1: 

The first model I designed was a baseline linear regression model to predict how population, GDP per capita(US dollars), and firespots related to Amazon deforestation totals.

My model predicted population, GDP per capita(US dollars), and firespots all as having an inverse relationship with my target variable of total deforestation. This result was different than my correlation plot with regard to firespots. My model was very overfit with an 86% r2 score for my training data and a 44% r2 score for my testing data. This is probably due to the small amount of data fed into my model influencing a tight fitting to few individual data points. Because of the r2 scores, I do not necessarily trust the inverse relationship this model projected between firespots and deforestation. I plan to look at firespots in more detail in future models.

### Modeling 2:

Because firespots showed a correlation with Amazon deforestation of 83% in my correlation plot, I decided to do more firespots anaylsis in my next models regarding the 83% statistic as truth that more firespots have a strong chance of leading to greater deforestation.

Fire outbreaks had a predominant decline in volume between the years 1999-2019, but I noticed in my analysis there were years with a higher number of firespots than previous years that could negatively impact deforestation totals over time. 

For my second model creation I designed a function that formulates a dataframe with the number of firespots per month for a given year in a dataset and includes the minimum, maximum, and mean number of firespots per month for each of the previous years in the dataset combined to analyze how one given year of monthly firespot totals compares to other previous years of monthly firespots across all states.

I tested my dataframe function on the year 2019 because I used that more current year to do a lot of modeling analyses and comprehend firespots correlations between that year and previous years. I desired to know how 2019 compared to previous years in terms of firespot monthly totals to better understand if deforestation is increasing over time with relation to firespots. I graphed my analysis as well and provided the image in the images file.


The year 2019 generally had a lower than average number of firespots compared to total firespot averages for previous years between 1999-2019. However, the months of March and April had a number of firespots in 2019 that was higher than the maximum number of firespots for those months in previous years. The high number of firespots in March and April of 2019 suggests there are still times when firespot totals are reaching dangerously high levels. The numbers could be significantly problematic when related to the deforestation of the Amazon in Brazil for the future.

### Modeling 3:

For the next successive models, I continued to look at firespots and I generated time series for each Brazilian state encompassing the Amazon that displayed fire outbreak amounts per month and year. I graphed the time series together in the images file.

The group of time series graph above showed that most all of the Brazilian states follow similar seasonality trends. The Brazilian states of Mato Grosso, Para, and Rondonia appear to lead the group of trends with their high firespot totals. Seasonal firespot trends may influence seasonal deforestation totals.

I proceeded to use arima modeling procedures on each Brazilian state within the Amazon individually to predict the number of firespots per month for the year 2019 and interpret the impact firespots had on each Brazilian state within the Amazon in 2019. The Brazilian states of Amazonas and Roraima had higher total firespot outbreaks in 2019 than all previous years from the data provided. Also, the actual total number of firespots for these states in 2019 was higher than the predicted values for the number of firespots for these states in 2019.

## Conclusions

My full analyses lead me to the following conclusions:

- Deforestation has not necessarily decreased over time. Acknowledge high deforestation totals and strong seasonality trends of firespots particularly within the Brazilian states of Mato Grosso, Para, and Rondonia to mitigate further and continuing deforestation issues identified within these states.

- Recognize future implications of an unprecedented high number of firespots for the months of March and April and the states of Amazonas and Roraima in 2019. Prepare to provide forest evacuations if these firespot totals remain the same or increase in future years.

- Employ efforts to enforce stricter fire restrictions during strong firespot season to reduce deforestation.


## For More Information

- See the full analysis of my findings in Amazon.ipynb

- Contact me at vijaykumar.d876@gmail.com

## Repository Structure

????????? Images

????????? Amazon.ipynb

????????? AmazonRainforestPresentation.pdf

????????? README.md

