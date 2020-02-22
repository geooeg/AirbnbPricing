
## Project description

This project try to analyze the Airbnb dataset from Seattle to understand the listing price patterns and to make price predictions for a listing. The results we can draw from the analysis should support the pricing strategy for Airbnb listing in Seattle.

Exploratory data analysis are made to firstly understand the listing price distribution based on temporal and locational facts, and wether the review scores have a effect on the price.

User behavior is analysis for how often they review on the same listing, which reflects how often the users come back to a listing they visited before.

A regression model is trained using the dataset, the coefficients of the model are analyzed to define the important features that affect the price of the listing.

Due to the fact that the prices of different listing room types (entire apt/ private room/ shared room) should not be compared together, i trained model for each type. From the coefficients of the models we can see that the important features for each type are different.

##### There are 4 questions  i try to answer by applying data science analysis:
1. Are there areas in Seattle, that have more listings than other areas?
2. Are there areas in Seattle, that the price of listings are higher than other areas?
3. Which months in the year do more turists visit Seattle? How do the prices of the listing react on that?
4. How do the review scores effect on the listings?
5. Do users tend to visit the same listing again?
6. Which features of a listing have effects on the listing price?

#### Analysis results
1. Are there areas in Seattle, that have more listings than other areas? - yes: Central Area, Capitol Hill, Rainier Valley, Ballard have significantly more listings than other neighbourhoods.
2. Are there areas in Seattle, that the price of listings are higher than other areas? - yes: Listings in Central area, Downtown, cascade show higher prices
3. Which months in the year how more listings in Seattle? How do the prices of the listing react on that? - the analysis shows that there are more listings available in March and less availability in July, As a result the analysis shows that the listing price in July is higher that other months
4. How do the review scores effect on the listings? - generally speaking, most of the listings have high review scores (7 to 9), especially for shared rooms and private rooms. However, the number of reviews is an important factor for prices. For entire apt or house, it shows that the review score is important.
5. Do users tend to visit the same listing again? - very few users repeatedly visit the same listing, most of the users visit once in the year in seattle.
6. Which features of a listing have effects on the listing price? - for every type of listing is different, details can be found in the notebook.

## Project files

./Airbnb Seattle Pricing.ipynb - the jupyter note book which implements the analysis mentioned in the project description
./seattle - folder which contain the seattle Airbnb data
    ./listings.csv - the listings in seattle on Airbnb
    ./calendar.csv - the data of when the listing is available
    ./review.csv - review information for the listings in the listing.csv
./html - a HTML export of the notebook, it also contains all the figures in the notebook


## Used Libraries in the project
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import r2_score, mean_squared_error
from sklearn.model_selection import cross_val_score, GridSearchCV
from sklearn.metrics import classification_report, confusion_matrix
from sklearn.ensemble import RandomForestRegressor
from sklearn.preprocessing import MinMaxScaler
from sklearn.metrics import roc_auc_score
import geopandas as gpd
from shapely.geometry import mapping, shape, LineString, MultiPoint, Point
import mplleaflet
import seaborn as sns