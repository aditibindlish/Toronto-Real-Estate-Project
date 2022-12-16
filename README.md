# Toronto-Real-Estate-Project
##Project Description/Outline
Using MLS data, analyze housing benchmark prices for different types of homes in the GTA. 

##Research Questions to Answer
1.    What type of housing has gained in price growth over the years, and what has had a slower growth in price?  
2.    What were the highest prices of each property type over time, and which areas had these highest prices?
3.    What is the overall trend of property values in the GTA over time? (e.g. spikes in price, potential COVID influences in 2020, etc.) 
4.    How much time does it take each property type to double in value in each area? 
5.    Are these locations in and around Toronto or farther away in GTA?

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

###Q1: What type of housing has gained in price growth over the years, and what has had a slower growth in price?
--Split the Year over year change rate for each type of housing from the dataset
--Sort data for year over year change rate of each sperate years
--combine the data for year over year change rate and calculate the average for each year.

###Q1: Results
-- According to the dataset, the Apartment has the most growth between 2016 to 2017, but after that it has a significant decrased from 2018 to 2020, which has the lowest year over year change rate among all four type of housing in 2020. In the other hand, Town House has the most increased of the year over year rate change. 
-- The highest peak of all the growth are in 2017, and the lowest in 2018

###Q2: What were the highest prices of each property type over time, and which areas had these highest prices?
--Split out data by each type of housing
--Sort data by Date and by Benchmark prices in descending order
--Retain only the first row per Date (i.e. highest benchmark per date) 
--Determine unique values in the filtered dataset (the places with the highest prices) and plot the highest prices over time 

###Q2: Results
--Overall, for single family houses (detached and attached), we see the prices rise sharply during the 2017 housing bubble and then sharply come back down afterwards. However, for townhouses and apartments, they didn't really fall back down but instead continued to rise over the next few years.
--Peak prices tend to stay in the Toronto areas, with the highest prices in Toronto C12 (Bridle Path-Hoggs Hollow).
--For single family detached homes, prices peaked in April 2017 at $2.54M, followed by a steep decrease to a low of $2.1M before climbing back up. By March 2021, prices had climbed back up to $2.51M but had not surpassed the 2017 peak yet. Toronto C12 (Bridle Path-Hoggs Hollow) had the highest prices in this category across all months of data used. 
--For single family attached homes, prices peaked in May 2017 at $1.49M in Toronto C02 (Annex-Wychwood). Prices are higher than ever since 2015 at $1.68M in March 2021. The three most expensive areas in this category over time are Toronto C02, Toronto C09 (Rosedale-Moore Park), and Toronto C08 (Downtown East). 
--For townhouses, there was a steep increase in June 2017 when prices jumped $100k. The peak price occurred in October 2020 at $1.75M in Toronto C09. After prices passed the $1.5M mark, they have not had as much fluctuation and remained between $1.5M and $1.75M. The three areas with the highest prices in this category over time are Toronto C02, Toronto E02 (Beaches), and Toronto C09. 
--For apartments, there has bee na more gradual increase month over month than we saw in the houses. There has been a steady rise since July 2015 in prices, however a steep increase from Jan-July 2017 when prices hit $838k in Toronto C03 (Forest Hill-Oakwood). Prices continued to increase over time to a peak of $1M in February 2021 (Toronto C03). Before 2017, Toronto W02 (Junction-High Park) had the highest prices, but from then on Toronto C03 dominated prices for most months. 

###Q4: How much time does it take each property type to double in value in each area?
--Clean dataframe used to groupby locations and sort for location and prices for max and min prices
--First row is retained as max and min 
--These 4 category wise data frames are further manipulated to calculate ratio of max and min prices, which gives x times of price movement
--Duration is calculated using corresponding dates
--Duration is converetd to string tytpe and Days are extracted, further converted to years by dividing by 365
--This data is plotted on a bubble chart using ratio as size of bubbles, colormap as rainbow to clearly see different ratios as the sizes are not remarakbly different to naked eye

###Q4: Results : 
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

