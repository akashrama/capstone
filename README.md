# Mapping the Spread of Dengue Fever in South America Due to Global Warming
This project shows the spread of dengue fever in South America due to global warming. My overall goal is to use data from the past and use it to build a model that attempts to predict the future. 

My initial data, data about the past or the training data, comes from DrivenData. It gives different environmental conditions and the number of dengue fever cases in a given area for two cities in South America from 1990 to 2015. I use the NOAA climate model to get predictions on environmetal conditions in the future up to 2100.

The NOAA data has environmental variables for each latititude and longitued point daily from the year 2001 to 2100. The environmental variables are tasmax(max daily temp). tasmin(min datily temp), tas(average daily temp), and pr (amount of daily pr in Newtons). The NOAA data is in a NETCD4 file and I used xr to parse through it. The past data has over 24 different varialbes. To match the NOAA data, I only used these three variables from the past data. 

Using these variables I tried different machine learning models and concluded that RandomForrest is the best model to use. I use GridSearch to hypertune the different parameters. I then predicted on the NOAA data

To check the validity on using past data to predict the future, I did a temporal split. I use the first 70% of the data as training and the last 30% as the test data. I predicted on the training data using the RandomForrest model. To evaluate this data, I use MAE and I get 14.01

After getting the predictions from the RandomForrest model I matched it with the other variables and latittude and longitude. I exported this data to Tableau. There I created a HeatMap with a slider bar over time that mapped the data. The different squares represent an areas likely risk of dengue fever in the future. This model is a generalization and does not predict the amount of cases in the future. It attempts to represent the risk at a given area over time.

## ToDo

I want to incorporate other variables into the model. This will make the model a better predictor for the number of dengue fever cases. I attempt to use NVDI data but the data is sparse for all the latitude and longitude points in the NOAA climate model. There are other variables such as humidity and dew point that are better predictors of dengue fever cases, but there are no climate model that predict on that.

I need to obtain more past data other than only two cities. I scoured the internet alot for this by couldn't find any. I may be able to manufacture this. I can get yearly dengue fever cases for each country from project Tycho. I can get yearly envrionmental variables from DarkSky API. The one downfall I forsee is the lack of specific locations in projet Tycho. You can't generalize weather conditions for a whole country.

I want to go into different Tableau features and make the map look better.