# Surfs Up
## Overview 
I am interested in opening a surf and shake shop which will serve surf boards and icecream to locals and tourists in Oahu. I have some savings I want to invest but will still need real investors to come on board to get it off the ground. I have developed a business plan and reached out to an investor who is famous for his love for suring. However, this investor is concerned about the weather because he invested in a surf shop earlier in his career but the shop went out of operation due to bad weather. He did not ask for any weather analysis before investing in the first surf shop. He has therefore, asked me to run some analytics on a weather data set he has of this same Island in Oahu I want to open the surf shop. 

The weather data provided has been stored in a SQLite database. I performed some preliminary analysis on precipitation for the last 365 days. A plot of precipitation was created in chronological order to show the total precipitation for each day. I also provided some summary statistics on precipitation for the past year. 

I also performed temperature analysis on the most active station the past year for the investor. 
 
I finally used Flask to display the results of my analysis to the investor in a webpage. The application had 5 routes: Precipitation, Stations, Monthly Temperature, Statistics, and a welcome route that will orient the investor and his associates to the webpage.

Continuing further with the analysis, my investor wants more information about temperature trends before opening the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu so he can determine whether the surf and shake shop business will be sustainable year-round.

## Results
The summary statistics obtained fro the month of June is shown below:

![image1](https://github.com/GerlechJen/surfs_up/blob/main/Images/june_temps_statistics.png)

The summary statistics for December is also as seen below:

![image2](https://github.com/GerlechJen/surfs_up/blob/main/Images/december_temp_statistics.png)

From the analysis:
* There is a relatively small difference of about 3.9 °F between the average temperature in June and December.
* The maximum temperature recorded for the month of June(85°F) was greater than the maximum temperature recorded for December(83°F). 
* The minimum temperature recorded for the month of June(64°F) was greater than the minimum temperature recorded for December(56°F). 

## Summary 

Provide a high-level summary of the results and two additional queries that you would perform to gather more weather data for June and December.
The standard deviation for the temperature recordings for the month of june was 3.257  while the standard deviation for the month of December was 3.746. This means that the temperature measurements for December are more spread out or vary more. While the temperature measurements for June are closer together in value.



1. I could perform additional queries to obtain precipitation data in Oahu for the months of June and December using the two codes below:

```python
june_precipitation = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
june_precipitation
```

``` python
dec_precipitation = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
dec_precipitation
```
The summary statistics of this analysis after the two results are converted to a dataframe is also shown below:

![image3](https://github.com/GerlechJen/surfs_up/blob/main/Images/june_precipitation.png)


![image4](https://github.com/GerlechJen/surfs_up/blob/main/Images/december_precipitation.png)

These additional  queries help to obtain data which shows that the month of December had a higher  maximum precipitation of 6.42 compared to that of June which was 4.43. The average precipitations recorded for December was also higher (0.2168) compared to the average precipitation for  june (0.1364) 

This helps to draw a more detailed conclusion that Oahu is colder and has more rains in December compared to June. However, the difference in the tempertaure and precipitation between June and December are not huge, which makes this business proposal more appealing.

2. I could also perform additional query to obtain temperature data in Oahu for the months of June and December for each station.
 

