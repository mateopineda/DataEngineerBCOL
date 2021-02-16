# DataEngineerBCOL
Hi all

This repo has a simple data analysis initiated for BCOL marketing area

# Data source url 
https://www.kaggle.com/kentonnlp/2014-new-york-city-taxi-trips

# Jupyter Notebook url
http://35.226.138.102:8888/
###### TOKEN:f2258a3332e7753bdd170fa1892465b3411607e54735b222

# Project structure
###### Code
  -CaptureLogs.ipynb
  
  -TaxiTrip.ipynb
###### Data
  -NYmap.jpg
  
  -subsetTaxiTrip.csv
  
  -subsetTaxiTrip.json
###### Logs_Exception
  -TaxiTrip.log
  
# Context
It's a subset data on New York City Taxi Cab trips for 2014.

# Data model and dictionary
1. vendor_id	- object -  a code indicating the provider associated with the trip record

2. pickup_datetime	- object -  date and time when the meter was engaged.

3. dropoff_datetime	- object -  date and time when the meter was disengaged.	

4. passenger_count	- int64 -  the number of passengers in the vehicle (driver entered value).

5. trip_distance	- float64

6. pickup_longitude	- float64 -  the longitude where the meter was engaged.

7. pickup_latitude	- float64 -  the latitude where the meter was engaged.

8. rate_code	- int64

9. store_and_fwd_flag	- object -  This flag indicates whether the trip record was held in vehicle memory 
before sending to the vendor because the vehicle did not have a connection to the server - Y=store and forward
; N=not a store and forward trip. 

10. dropoff_longitude	- float64 -  the longitude where the meter was disengaged.

11. dropoff_latitude	- float64 -  the latitude where the meter was disengaged.

12. payment_type	- object

13. fare_amount	- float64

14. surcharge	- float64

15. mta_tax	- float64

16. tip_amount	- float64d	

17. tolls_amount	- float64

18. total_amount	- float64

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

# Question
¿Is the high vehicular traffic of NY product of a lack in mobility alternatives on specific parts of the city?

# Tools and technologies 
In this case i use GCP IaaS creating a VM instance having a deep learning image on linux with tensorflow, 
cause that provides me immediately a ready to run environment. After configure a firewall rule and define
an static ip then i started a Jupyter Notebook with following command
###### jupyter notebook --ip=0.0.0.0 --port=8888 --no-browser &
Jupyter Notebooks it's a very good option when we are still in the prototyping phase and has support for
Julia, Python, and R. In this case im using Python for my experience working on and knowledge of librarys.
Apart of that, basic libraries in using like pandas for data structures, matplotlib for plotting and logging 
for logs and exceptions storage

Please if you want also check following image Arch.jpg stored in this repo for additional info

# Data Updates
data updates frequency for this analysis table should be daily as many events can do a change in traffic like 
infrastructure changes on the city, sport events, holidays, and so on

# Cloud DataFlow (DataPipeline)
console.cloud.google.com/dataflow/jobs/us-central1/2021-02-15_18_09_49-17407678537988426797?pageState=(%22dfTime%22:(%22s%22:%222021-02-16T02:09:54.658Z%22,%22e%22:%222021-02-16T02:18:31.133Z%22))&project=dataenginnerbancolombia

Please if you want also check following images dataflow.jpg, dataflowJobs.jpg and dataprep.jpg stored in this repo 
for additional info

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
