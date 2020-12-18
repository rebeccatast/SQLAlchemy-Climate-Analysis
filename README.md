# SQLAlchemy
After making the decision to take a vacation in Honolulu, Hawaii, it was time to do some vacation planning by running a climate analysis on the area using Python (Pandas and Matplotlib) and SQLAlchemy ORM queries. 

## Climate Analysis
I first completed an analysis of the precipitation in the area using Python. The query retrieved the last 12 months of precipitation data. Using only the date and prcp values, I loaded the query results into a Pandas DataFrame, indexed to the date column. The DataFrame was then sorted by date and plotted. Pandas was also used to print the summary statistics for the precipitation data. 

## Station Analysis
I then designed a query to calculate the total number of stations, find the most active stations, and retrieve the last 12 months of temperature observation data (TOBS). These queries included:

  - Listing of stations and the observed counts in descending order. 
  - The station with the highest number of observations overall. 
  - The station with the highest number of observations over the last 12 months. 

In addition, I created a histogram showing the TOBS data over the last 12 months. 

## Climate App
After completing the initial analysis, I designed a Flask API based on the queries develped in Python. Using Flask, I created the following routes:

  - /
    - This created the Home page and all available routes.
  - /api/v1.0/precipitation
    - In this section I converted the query results to a dictionary, using date as the key and prcp as the value, and returns a JSON representation of my dictionary. 
  - /api/v1.0/stations
    - Returns a JSON list of stations from the data. 
  - /api/v1.0/tobs
    - Creates a query of the dates and temperature observations of the most active station for the last year of data, and returns a JSON list of the TOBS for one year. 
  - /api/v1.0/<start> and /api/v1.0/<start>/<end>
    - Returns a JSON list of the minimum temperature, average temperature, and the max temperature for a give start and end range, including given only a start date and given a start and end date. 
  
  
