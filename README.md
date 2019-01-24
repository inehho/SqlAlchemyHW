# SqlAlchemyHW
This is repository demonstrates the use of Python and SQLAlchemy to do basic climate analysis and data exploration on a climate database. 

All of the following analysis were completed using SQLAlchemy ORM queries, Pandas, and Matplotlib.

--> SQLAlchemy to create_engine for connecting to my sqlite database.
--> SQLAlchemy automap_base() to reflect tables into classes and save a reference to those classes called Station and Measurement.

Precipitation Analysis
--> Designed a query to retrieve the last 12 months of precipitation data.
    Selecting only the date and prcp values.
--> Load the query results into a Pandas DataFrame and set the index to the date column.
--> Plot the results using the DataFrame plot method.
    Used Pandas to print the summary statistics for the precipitation data.

Station Analysis
--> Designed a query to calculate the total number of stations.
--> Designed a query to find the most active stations.
    List the stations and observation counts in descending order.
--> Designed a query to retrieve the last 12 months of temperature observation data.
    Filtered by the station with the highest number of observations.

Temperature Analysis
--> Defined calc_temps function to calculate the min, avg, and max temperatures for trip using the matching dates from the previous year.
--> Plot the min, avg, and max temperature from your previous query as a bar chart.




Creating the Climate App
Designed a Flask API based on the queries that have just been developed.
Used FLASK to create routes.

Routes
/api/v1.0/precipitation
Converted the query results to a Dictionary using date as the key and prcp as the value.
Returned the JSON representation of my dictionary.

/api/v1.0/stations
Returned a JSON list of stations from the dataset.

/api/v1.0/tobs
Query for the dates and temperature observations from a year from the last data point.
Returned a JSON list of Temperature Observations (tobs) for the previous year.

/api/v1.0/<start> and /api/v1.0/<start>/<end>
Returned a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.
