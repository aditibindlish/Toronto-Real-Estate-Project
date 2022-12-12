# Toronto-Real-Estate-Project
##Project Description/Outline
Using MLS data, analyze housing benchmark prices for different types of homes in the GTA. 

##Research Questions to Answer
1.    What type of housing has gained in price growth over the years, and what has had a slower growth in price?  
2.    Has any area in the GTA had negative growth in price over time?
3.    What were the highest prices of each property type over time, and which areas had these highest prices?
4.    What is the overall trend of property values in the GTA over time? (e.g. spikes in price, potential COVID influences in 2020, etc.) 
5.    How much time does it take each property type to double in value in each area? 
6.    Are these locations in and around Toronto or farther away in GTA?

##Datasets to be Used
https://www.kaggle.com/code/alankmwong/exampletorontohousingindex

###Rough Breakdown of Tasks
1.    Data cleaning - state assumptions used/steps taken  
1.    checking data types
2.    looking at misspelled location names
3.    missing data fields - what to do with numerical missing fields, Barrie has no data for 2020
2.    Summarizing data for each question, creating charts/graphs for each question (2 per)
3.    Conclusion statements
4.    Powerpoint/Presentation - together on Thursday 

###Q3: What were the highest prices of each property type over time, and which areas had these highest prices?
--Split out data by each type of housing
--Sort data by Date and by Benchmark prices in descending order
--Retain only the first row per Date (i.e. highest benchmark per date) 
--Determine unique values in the filtered dataset (the places with the highest prices) and plot the highest prices over time 

###Q3: Results
--For single family houses (detached and attached), we see the prices rise sharply during the 2017 housing bubble and then sharply come back down afterwards. However for townhouses and apartments, they didn't really fall back down but instead continued to rise over the next few years
--Peak prices tend to stay in the Toronto areas, with the highest prices in Toronto C12 (Bridle Path-Hoggs Hollow)

###Q5: How much time does it take each property type to double in value in each area?
--Clean dataframe used to groupby locations and sort for location and prices for max and min prices
--First row is retained as max and min 
--These 4 category wise data frames are further manipulated to calculate ratio of max and min prices, which gives x times of price movement
--Duration is calculated using corresponding dates
--Duration is converetd to string tytpe and Days are extracted, further converted to years by dividing by 365
--This data is plotted on a bubble chart using ratio as size of bubbles, colormap as rainbow to clearly see different ratios as the sizes are not remarakbly different to naked eye

###Q5: Results : 
--Oshawa was the only location where prices doubled for all categories
--Prices doubled in 5yrs to 5.7yrs for most locations, many apartments saw doubling in price in <5 yrs
--quickest doubling seen in apartments, also maximum 20 locations saw price doubling in apartments, townhomes 16 (3 locations <5yrs), detached 15, attached 11
--Oshawa highest in attached (2.3x) and townhouses (3x), areas in toronto in detached (4x) and apartments (2.4x)

###Q5: Are these locations in and around Toronto or farther away in GTA?
--final data frames from above analysis are further manipulated and used in a for loop
--GeoApi's geocoding API has been used to extract latitude and longitude for each city in the dataframe for each category
--these lat and long are stored in a dictionary containing city name
--this dict is converted to a dataframe and using HVplot plotted on OSM tile using Geoviews module and HVplot library in Pandas

###Q5: Results : 
--Locations in entire GTA saw price doubling, not just Toronto or nearby areas
--No concentration is apparent in area or direction towards Toronto City, infact, most areas are away from the densely populated Toronto

