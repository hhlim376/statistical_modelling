# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
To extract meaningful data from APIs and work with that data to build a statistical model and intepret the results of the statistical model.

&nbsp;



## Process
&nbsp;

### Step 1: Work with CityBikes API
* Query the city bikes API to find the network id for bike stations in the city of Vancouver
* Using the network id, retrieve all available bike stations in the city of Vancouver
* Use the API to query the latitude, longitude and number of bikes for each bike station and parse this information into a Pandas dataframe
&nbsp;
### Step 2: Working with Foursquare and Yelp APIs
* Query the Yelp and Foursquare APIs for information on POIs in a radius surrounding the bike stations from Part 1
* Put the POI information into dataframes
* Answer notebook questions using the information retrieved
&nbsp;
### Step 3: Joining Data
* Join data from Part 1 and 2 into a single dataframe
* Explore the data by creating vizualisations using tools such as seaborn
* Create and SQLite database and store data in it
&nbsp;
### Step 4: Build a model
* Build a regression model that demonstrates a relationship between the number of bikes in a particular location and charecteristics of POIs in that location
* Intepret the results of the model
&nbsp;
### Note: The code used for these steps as well as more in-depth logic/explanations can be found in the associated notebooks in the notebook folder. Additionally, there are a couple notebooks in the rough_work folder that contains test code and code I used for unit testing. These notebooks can be ignored!
&nbsp;


## Results
&nbsp;
### Comparative coverage of API results: Yelp vs Foursquare
* Overall I felt Foursquare had the better coverage
* Foursquare returned more results for number of POIs in an area compared to Yelp
* Foursquare also returned more attributes for the POIs I was interested in
* For the rating and price point of POIs, I prefered Foursquares scaling as it was a continuous scale whereas Yelp used a discrete scale
&nbsp;

### Model Results
* After going through a backward selection process, the final model I settled on was a Simple Linear Regression model with number of cafes as the independant variable and number of bikes as the dependant variable
* While this model had the highest adjusted R-squared value of all the models I tested, the final R-squared value was still incredibly low: only 0.048
* This means that for all the independant variables I tested, none made for good predictors for number of bikes in an area
* For more in-depth thoughts on the model, please see the model_building notebook in the notebooks folder
&nbsp;

## Challenges 
* The Foursquare API had a limit of 50 results, so for example, if there were more than 50 cafes in a specified location, it would only return details of up to 50
* For the independant variables I chose, none of them made for good predictors for the dependant variable

&nbsp;

## Future Goals
&nbsp;
### Building a better model
* For this project I spent alot of time trying to figure out how to code the things I wanted to do (how to extract the info i wanted from JSONs, how to organize and join the data I wanted etc.) and so I settled on only 8 independant variables.
* Now that I am more comfortable with the process, in the future and with more time, I would like to upscale everything and query for more POIs 
* This would lead to a better chance of finding an independant variable that would make for a good predictor for our dependant variable
&nbsp;
### Outliers
* For this project, some of the data I looked at had some extreme values, however I made the decision not to remove them as it seemed that there were enough of them that they wouldnt truly count as outliers
* If I had more time, I would probably like to examine this issue more carefully to see if I should have removed them after all
