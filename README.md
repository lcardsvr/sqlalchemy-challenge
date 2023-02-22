# Module 10 Challenge


## Instructions

Congratulations! You've decided to treat yourself to a long holiday vacation in Honolulu, Hawaii. To help with your trip planning, you decide to do a climate analysis about the area. 

## Part 1: Analyse and Explore the Climate Data

### Precipitation Analysis

The most recent date in the dataset is: 

----- Latest Date-------

('2017-08-23',)

With this date query date range was set as "query_date = dt.date(2017, 8, 23) - dt.timedelta(days=365)"

The required analysis is in the jupyter notebook under https://github.com/lcardsvr/sqlalchemy-challenge/blob/main/SurfsUp/climate_starter.ipynb.

A snip of the maximum precipitation per day is presented below.

![image](/precipitation_max_plot.png)


A summary of the precipitation data is below:

| count |	2021.000000 |
| ---- | -----|
|mean |	4.505888|
|std|	11.713487|
|min|	0.000000|
|25%	|0.000000|
|50%|	0.500000|
|75%	|3.300000|
|max	|170.200000|

The summary per station for the year is below:


| Station Name | Min Prcp| Max Prcp| Average Prcp | Count |
| -------------| -------- | ------- | ---------- | ------ |
|'USC00519397'| 0.0| 66.5| 1.1417827298050147| 359|
 |'USC00519281'| 0.0| 75.7| 5.056534090909081| 352|
 |'USC00516128'| 0.0| 170.2| 11.450914634146345| 328|
 |'USC00513117'| 0.0| 73.7| 3.593877551020405| 343|
 |'USC00519523'| 0.0| 158.8| 3.077070063694266| 314|
 |'USC00514830'| 0.0| 60.7| 3.1890566037735826| 265|
 |'USC00517948'| 0.0| 61.0| 1.9449999999999998| 60]

### Station Analysis

Count of measurements per station
| Station Name | Count|
| -------------| -------- | 
|'USC00519281'| 2772|
 |'USC00519397'| 2724|
 |'USC00513117'| 2709|
 |'USC00519523'| 2669|
 |'USC00516128'| 2612|
 |'USC00514830'| 2202|
 |'USC00511918'| 1979|
 |'USC00517948'| 1372|
 |'USC00518838'| 511|

 Summary of min, max and average per station (degC)

| Station Name | Min Temp| Max Temp| Average Temp | 
| -------------| -------- | ------- | ---------- | 
 |'USC00519281'| 12.2| 29.4| 22.03582251082252|
 |'USC00519397'| 13.3| 30.6| 23.643098384728138|
 |'USC00513117'| 15.0| 29.4| 22.602141011443422|
 |'USC00519523'| 13.3| 29.4| 23.634057699512883|
 |'USC00516128'| 14.4| 28.9| 21.62166921898927|
 |'USC00514830'| 14.4| 29.4| 23.817756584922684|
 |'USC00511918'| 11.7| 30.6| 22.00919656392112|
 |'USC00517948'| 14.4| 30.6| 23.712172011661778|
 |'USC00518838'| 14.4| 28.3| 22.623287671232877]


The most active station was USC00519281.
The minimum temperature for the station was 12.2 degC.
The maximum temperature for the station was 29.4 degC.
The average temperature for the station was 22.03582251082252 degC.

The histogram for the last year temperature measurements for USC00519281 is below.

![image](/temperature_plot.png)

##  2: Design Your Climate App

The code for the app is available under https://github.com/lcardsvr/sqlalchemy-challenge/blob/main/SurfsUp/app.py

The main page will provide the information below:

Available Routes:


1. To get the Jsonified precipitation data for the last year in the database :
/api/v1.0/precipitation


2. Jsonified data of all of the stations in the database :
/api/v1.0/stations


3. Jsonified last year of data for the most active station (USC00519281) :
/api/v1.0/tobs


4. Min, max, and average temperatures calculated from the given start date to the end of the dataset. Input format must be numbers separated by a hyphen following Year-MM-DD format:
/api/v1.0/Year-MM-DD


5. Min, max, and average temperatures calculated from the given start date to the given end date. Input format must be numbers separated by a hyphen following Year-MM-DD format:
/api/v1.0/Year-MM-DD/Year-MM-DD

For the queries data is available between 2010-01-01 and 2017-08-23


## Submission

1. Submitted and available in GitHub under https://github.com/lcardsvr/sqlalchemy-challenge

2. Surfsup Jupyter Notebook available under https://github.com/lcardsvr/sqlalchemy-challenge/blob/main/SurfsUp/climate_starter.ipynb

3. Code for the App available under https://github.com/lcardsvr/sqlalchemy-challenge/blob/main/SurfsUp/app.py



