# Project: Analyzing the Societal, Health, and Environmental Impacts of Energy
### Members:
- Artien Voskanian
- Claire Fraser
- Alexis Clark (AC)
- Taylor Griggs
- Pete Kline

### Overview of Analysis
This project seeks to uncover the significant effects of energy type and consumption on diverse aspects of life, including weather patterns, public health, and poverty alleviation, aiming to weave a compelling narrative across these dimensions
That regions with higher levels of renewable energy production correlate with improved physical health among residents; 
And that leveraging machine learning algorithms can forecast future shifts in energy demands based on historical data, including the prediction of fuel poverty among segments of the population. 

### Hypotheses
- Weather patterns significantly influence energy consumption, with states with the highest and lowest temperatures exhibiting the highest energy usage. 
- States with greater amounts of renewable energy consumption correlate with improved physical health among residents. The metric for health considered in this evaluation is cancer. 
- Machine learning models can predict future changes in energy requirements based on historical weather data.
- Machine learning models can predict an increase or decrease in cancer rates when compared to historical cancer data. Improving energy efficiency may be more effective than increasing production in mitigating energy consumption and environmental impacts.
- Enhancing energy efficiency may yield greater dividends in reducing cancer rates and mitigating environmental impacts compared to simply enhancing production capacities.
- Through rigorous investigation and analysis, we endeavor to illuminate pathways toward a more sustainable energy future.

### Data Visualizations

We reviewed 10yrs of weather data utilizing the Open-Meteo weather API, and graphed the results. As anticipated, more northern states and states at higher elevation states were coldest on average. And more coastal or southern states were hotter on average. But we needed to find if these states were in fact large users of energy to prove our hypothesis.

![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/claire/combined_heatmap.png)


### Fossil Fuel Energy Consumption
We pulled data from the Energy Information Administration and when we compare the levels of total fossil fuel consumption by state, we see some striking differences. The amount of fossil fuel consumption in Texas exceeds California by almost 2x the amount. The key contributors in the later years seem to be from petroleum and gas consumption, as coal energy consumption seems to decline over 10 years for almost all states.

##### Total Fossil Fuels
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/ac/energy_by_types_visuals/annual_total_fossil_fuel_consumption_top_10_US.png)

##### Coal Consumption
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/ac/energy_by_types_visuals/annual_coal_consumption_top_10_US.png)

##### Petroleum Consumption
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/ac/energy_by_types_visuals/annual_petroleum_consumption_top_10_US.png)

##### Natural Gas Consumption
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/ac/energy_by_types_visuals/annual_gas_consumption_top_10_US.png)

##### Nuclear Consumption

![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/ac/energy_by_types_visuals/annual_nuclear_consumption_top_10_US.png)



### Renewable Energy consumption
From 2015 to 2020, California had the highest amount of total renewable energy consumption. What is interesting is that when we reached 2020, the consumption in Texas brought the state up to second rank. This increase over time seems to mirror the increase seen in the wind energy plot, likely due to the numerous wind farms in the state of Texas. Washington state had the highest total renewable energy in 2011–likely due to hydropower, however the level seemed to slightly decrease overtime which is interesting

#### Annual Total Renewable Consumption
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/ac/energy_by_types_visuals/annual_total_renewable_consumption_top_10_US.png)


#### Fossil fuels vs renewables - 10yr
States with high energy consumption are adjusting to evolving demands and changing weather patterns. They are actively decreasing the production and consumption of non-renewable resources while investing in renewable energy sources instead…with Texas telling an interesting story

#### Fossil Fuel Change By State Over 10 Year Period
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/Resources/fossil_change_by_state.png)


#### Rates of All Cancer Types
We analyzed and plotted all 50 states rates per year from 2010 to 2020
On the left the box plot states that as a nation we saw an increase amongst all cancer types as a rate per year.
So we dove into a linear regression analysis of the rates. 

##### Box Plot
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/claire/allcancer_rates.png)

#### All Cancer Rates - Top Bottom 10
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/claire/allcancer_rates_topBottomTen.png)


#### Cancer Rate Linear Regression
Looking at the linear regression data we were able to compare rate of change to rate of change rather than individual points. It created a best fit line between the differing rates.
As you can see, the green states show a linear regression that assumes a decrease in cancer rates per population from the prior years
On the flip side we say that the red states were showing a linear regression that shows an increase in cancer rates from the prior years.

![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/taylor/Lower48rate.png)


#### Lung & Bronchus Cancer 

##### Lung Cancer Rates
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/claire/lungcancer_rates.png)

##### All Lung & Bronchus Cancer Rates - Top Bottom 10
![AltText](https://github.com/fraserclaire/Group3_Project4/blob/main/claire/lungBronchalCancer_rates_topBottomTen.png)

#### Lung & Bronchus Cancer Rate - Linear Regression
We then repeated the process with Lung and Bronchus Cancer
The box plot on the left shows a rather stagnant rate change over the years 2010 to 2020
The states in color on the right graph show the highest cancer rates.
While the gray points show the the lowest rates across the nation

<enter pics lung and bronchus cancer rates>



### Data Modeling

#### Model 1: Weather Model
- Objective: Predict if Renewable Energy Consumption Rate is High or Low
- Input Features: latitude, longitude, average max temp, average min temp, average daylight hour, average rain, average snow, fossil fuel consumption, and total renewable consumption.


#### Model: Random Forests
- Recall: 86%
- Accuracy: 93%
- f1-score: 92%
- Model 2: Cancer-Energy Model
- Objective: Predict if Lung/Bronchal Cancer Rate is Increasing or Decreasing
- Input Features: Energy production data by type (Fossil Fuels vs Renewable)


#### Model 2A: Random Forests
- 3 iterations
- Average accuracy: 77.2%
- Best accuracy: 84.6%

- Model 2B: Neural networks
- 3 iterations
- Accuracy: 92.3%
- Loss: 0.49



### Results
Of the 10 hottest states in the US, we found that 6 were top consumers of renewable energy, and 4 were top consumers of fossil fuels. However, the 10 coldest states tell a different story. Among the states listed, only one stood out as a primary consumer of renewable energy, while another emerged as a prominent consumer of fossil fuels.

According to our linear regression analysis, we anticipate a decline in lung cancer rates per capita in six out of the ten states with the highest utilization of renewable energy. Conversely, in opposition to our hypothesis, only two out of the ten states with the greatest reliance on fossil fuels were expected to experience an uptick in their lung cancer rates.
Our machine learning algorithms were able to predict a state’s renewable energy consumption (high or low) as well as predicting its increase/decrease in lung cancer per capita based on previous data.


### Summary

We have examined energy consumption in the United States through the perspectives of weather and public health in an attempt to discover any plausible correlations that may exist between these topics. We believe that while weather may influence a state's energy consumption, there are likely other significant factors at play. Among these factors, the population size of a state is likely to be particularly significant.
Finally, we set out to find any relationship between energy type and lung cancer at a state level. Once again, while we acknowledge the potential impact of energy types on the lung cancer rates within a state, we recognize the existence of numerous other factors of varying significance that may contribute to this outcome. 



### Additional resources 
https://public.tableau.com/app/profile/pete.kline/viz/Energy_and_Weather/WeatherMinList


https://public.tableau.com/app/profile/taylor.griggs/viz/CancerRates_17127924919080/LungRates


https://public.tableau.com/app/profile/taylor.griggs/viz/ratesPlot/2010-2020CancerRates

ChatGPT - SHOUT OUT

