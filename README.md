
# Diverse Real Estate Investing

Analyst: Shannon McChesney
Tableau Presentation: https://public.tableau.com/views/DiverseRealEstateInvestingStory/DiverseRealEstateInvestment?:language=en&:display_count=y&publish=yes&:origin=viz_share_link
Blog Post: https://samcches.github.io/diverse_real_estate_investing

## Introduction

Everyone has different needs, just as they have different experiences and different lifestyles. In the same vein, every investment portfolio should be unique to the needs of the investor. Some feel a great deal of pride investing in locally, while for others location is not important. Those looking for solid, proven investments that continue to grow will look for the equivalents of Apple and Google to place their money, while those who find excitement in uncovering investments that have more potential will search for opportunities than have yet to show their greatest growth.
The same concepts apply to real estate investing.
Using data from the property-selling site Zillow, I calculated the best investment opportunities in four categories: local + proven, local + potential, national + proven, and national + potential. As New York City is my home base, I used it as the local investment city.

## Procedure

* Load the Data / Filter Out Chosen Zip Codes
* Preprocess Data
* EDA & Visualization
* Reshape the Dataframe
* ARIMA Modeling

### Step 1: Load the Data / Filter Out Chosen Zip Codes
After all the necessary libraries were imported and the data loaded to a pandas dataframe, the next step is to create a separate dataframe solely for the properties in the New York Metropolitan area, to be used for the local properties analysis.

### Step 2: Preprocessing the Data
I then converted the date column to  date/time format, counted and disposed of null values, and determined the number of properties per zip code.

### Step 3: EDA & Visualization
Before visualizing our data, I needed to explore the data and calculate the percent change in each zip code. Each of these percent changes were saved as data frames, and the five largest percent changes in the positive and negative ends of local and national categories were plotted as line graphs.

### Step 4: Reshaping the Dataframe
Reshaping the data frame is required when preforming a time series analysis. In this process, the dates become the vertical axis, while the the values (in this case, the values of each zip code) also becomes a singular column rather than a row. After this, we can proceed with our ARIMA modeling.

### Step 5: ARIMA Modeling
The first step in ARIMA modeling is to test for stationarity. This allows us to see the growth or decline in value irrespective of time. Then the optimum values of the AR order, the degree of differencing, and the MA order are calculated in order to create the best ARIMA model for the data. The output of the model can then be plotted for diagnotics. 

### Conclusion
The top five zip codes for each investment category are as follows:

* Local + Proven: 11233 (Brooklyn, NY), 11216 (Brooklyn, NY), 07306 (Jersey City, NJ), 07307 (Jersey City, NJ), 11963 (Noyack, NY)
* Local + Potential: 07462 (Vernon, NJ), 07422 (Highland Lake, NJ), 12594 (Dover, NY), 07418 (Vernon Valley, NJ), 10526 (Goldens Bridge, NY)
* National + Proven: 30032 (Candler-Mcafee [Atlanta], GA), 33805 (Lakeland, FL), 37210 (Nashville, TN), 15201 (Pittsburgh, PA), 27980 (Hertford, NC)
* National + Potential: 48506 (Flint, MI), 48503 (Flint, MI), 78735 (Austin, TX), 15902 (Johnstown, PA), 61012 (Capron, IL)

### Further Research
* Look into corporate rehabilitation of the National + Potential cities (ex. Google/Amazon replacing all of the water pipes in Flint, MI and purchasing the houses of current residents to create a tech city while being socially responsible).
* Analyze whether the Proven categories are “socially responsible” investments.
* Investigate the extent to which the zip codes suggested in this recommendation will withstand the effects of climate change over the next 30 years (the age of the average mortgage)