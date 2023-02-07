# wind-energy-power-prediction
A predictive modelling project for estimating power generated on a wind farm based on the wind and other weather data available for that farm.

<<<<<<< HEAD
=======
**NOTE:** *My final code push update will be done on Tuesday evening as I'd been away for staycation on the weekend, and forgot to put in the charger of laptop while packing up stuff. I've updated the summary and initial code github link through my phone now.*
>>>>>>> fbdbdbb1ef4be7b0a0b3cdf996c63718afb55139

# General Introduction:

In recent years an increasing number of countries have implemented policy measures to promote renewable energy. The evolution of wind power generation is being produced with a very high growth rate at world level (around 30%). 

It is quite clear that wind as a renewable resource should be competitive with conventional power generation sources. It is also the most deserving of all of the cleaner energy production options (geothermal, solar, tidal, biomass, hydro) for more widespread deployment. 

Although wind power is a never ending green resource, it does have its own drawbacks which are related to its discontinuous, unpredictable supply. There'll be days when the wind is strong and continuous, and other days when it's not. We need to deal this problem into account very seriously for us to be able to keep providing uninterrupted power supply to homes/offices incase of shortage or disruption of power. 

# Project Objective:

That is where the main objective of the project comes in:

1. Developing a forecasting model for wind renewable energy production by using historical data on weather conditions and renewable energy production. Here we develop a machine learning model that could be trained to predict future renewable energy production. This could be used by utilities and energy companies to better plan for and manage the integration of renewable energy into the grid.

2. Optimizing energy storage: With the help of weather forecast and historical data, a model could be developed to predict the shortage or excess of energy production and then optimize the energy storage system to plan alternate energy supply source to be switched, for the former and store that excess energy for the latter to be used later which could help in reducing the dependence on non-renewable sources.

# Project Development Description:

## Data Gathering:

+ Firstly, we had to explore the exhaustive list of wind farms around the world. The data for the wind farms was found on the portal :

https://www.thewindpower.net/index.php

The collection of the windfarms data (hyperlinks) are done through web scraping. The pages were navigated page by page and the collection of their page links were made into a list. 

+ Later, each link is traversed and scraped to gather the windfarm stats like: no. of turbines, expected power generation, its latitude and longitude, and saved again into a list.

<<<<<<< HEAD
+ Now, for each latitude, longitude retrieved, we call the Web API to gather all the weather information. 

Now we concatenate the features we retrieved and the output information (power per turbine) and prepare our dataset.
=======
+ Now, for each latitude, longitude retreived, we call the Web API to gather all the weather information. 

Now we concatenate the features we retreived and the output information (power per turbine) and prepare our dataset.
>>>>>>> fbdbdbb1ef4be7b0a0b3cdf996c63718afb55139

## EDA:

We explore the distribution of values in each input feature through distribution plots and ox plots. We realize there were few countable outliers in every input feature. We decide to remove them as they were less than 1%. Removing outliers from each of the input feature would still sum up to less than 1% of the total no. of rows. 

I used numpy percentile method to do so only if the outliers lied on both sides of the bell curve (50% percentile), and manual filtering conditions otherwise. 

A few interesting insights were also brought up by plotting the graphs on the Tableau:

+ Regression plots showed that the wind direction was more correlated to the output column, than the speed
+ The input feature value range for each column had a specific range where majority of the wind farms operated. 

<<<<<<< HEAD
This could mean that the wind farms shared a common characteristic amongst themselves and that range characteristic could come in very handy while deciding a potential wind farm site. 
=======
This could mean that the wind farms shared a common characteric amongst themeselves and that range characteric could come in very handy while deciding a potential win farm site. 
>>>>>>> fbdbdbb1ef4be7b0a0b3cdf996c63718afb55139

One interesting insight which was observed after plotting the distribution plot on wind direction was on the specific range of wind direction of the windfarms, which turned out to be in between 180-270. This direction corresponds to the winds coming from 3rd quadrant OR  in geographical terms, from South West. And since most the countries collected in the dataset are from Europe, the wind direction possibly mean the winds from Atlantic ocean which drives most of the wind energy generation in the continent. 

## Model Building:

<<<<<<< HEAD
The dataset is later scaled, transformed and split into train test datasets and a regression model is built. The best model is chosen through a model pipeline by trying a series of models along with cross validation. 

We tried both linear model and the random forest regress or and tested the accuracy.

## Code and Data Files Guide:

### Main Files:

    nasa-power-api-scrapper-daily-weather-info.ipynb

This script scraped the input features - historical weather data (temperature, humidity, wind etc.)

    wp-wf-output-power-data-scraping-pipeline.ipynb

This script scrapped the output value (power generated by the wind farm in that month).

    wind-power-predictive-modelling.ipynb

This script used the dataset collaborated above to develop a predictive model for predicting the wind power generated based on the wind data available for the windfarm for that particular month.

 ### Tableau Link:

[EDA of Wind Farms](https://public.tableau.com/app/profile/nipun.bhushan/viz/scraped-windfarms-statistics-dashboard/BubbleMapofWindpowerGenerationperWindFarm)

[Wind Power by Country Statistics](https://public.tableau.com/app/profile/nipun.bhushan/viz/wind-power-countries-statistics/Dashboard)
=======
The dataset is later scaled, transformed and splitted into train test datasets and a regression model is built. The best model is chosen through a model pipeline by trying a series of models along with cross validation. 

We tried both linear model and the random forest regress or and tested the accuracy.

The data gathering was done in 2 sections. For the features collection, basically the weather data (predominantly wind data : speed, direction and several other columns) was done through Web API. Thendat



>>>>>>> fbdbdbb1ef4be7b0a0b3cdf996c63718afb55139
