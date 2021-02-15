# DataEngineerBCOL
Hi all

This repo has a simple data analysis initiated for BCOL marketing area

# Data source url 
https://www.kaggle.com/kentonnlp/2014-new-york-city-taxi-trips

# Context
It's a subset data on New York City Taxi Cab trips for 2014.

# Content
1. vendor_id	

2. pickup_datetime	

3. dropoff_datetime	

4. passenger_count	

5. trip_distance	

6. pickup_longitude	

7. pickup_latitude	

8. rate_code	

9. store_and_fwd_flag

10. dropoff_longitude	

11. dropoff_latitude	

12. payment_type	

13. fare_amount	

14. surcharge	

15. mta_tax	

16. tip_amount	

17. tolls_amount	

18. total_amount

# Data Size
2.36 GB

# Format
csv

# Filename 
nyc_taxi_data_2014.csv

# Purpose 
With "NY Taxi Trips" dataset, i want to build an analysis table trying to identify zones where a 
trip starts and ends in most of the cases, with that information the district administrations will 
search for different alternatives in transportation on those zones, having as a main purpose, reduce 
the traffic on NY city

# Questions
¿Is the high vehicular traffic of NY product of a lack in mobility alternatives on specific parts of the city?

¿How much time and money on average people are investing to travel between those critical points?

# Tools and technologies 
In this case i use GCP IaaS creating a VM instance having a deep learning image on linux with tensorflow, 
cause that provides me immediately a ready to run environment. After configure a firewall rule and define
an static ip then i started a Jupyter Notebook with following command
###### jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser &
Jupyter Notebooks it's a very good option when we are still in the prototyping phase and has support for
Julia, Python, and R. In this case im using Python for my experience working on and knowledge of librarys.
Apart of that, basic libraries in using like pandas for data structures, matplotlib for plotting and logging 
for logs and exceptions storage

# Data Updates
data updates frequency for this analysis table should be daily as many events can do a change in traffic like 
infrastructure changes on the city, sport events, holidays, and so on

# Scalability in case of 100x
As we are working only in a subset of 15% original dataset, expecting a 100x additional data 
in the original one means we have different data sources like Mobile, Web, Databases and IoT, in that
case use Cloud Pub/Sub and for filter, clean and transform use Cloud DataFlow storing finally 
in BigQuery, all fulled management by GCP

# Running data pipelines daily at 7am
I suggest to connect Cloud Run to our data pipeline giving the required schedule of 7am

# Database concurrency for more than 100 persons
In case of extensive activities by many users at same time, will be a better approach use distributed 
databases with certain independence and capable to implement solutions with parallelism 
