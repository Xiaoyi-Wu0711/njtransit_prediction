---
title: "Analysis by Location "
date: 2021-12-20
published: true
tags: [dataviz, altair, folium]
excerpt: "Where does the delay usually occur?"
altair-loader:
  altair-chart-1: "charts/station_time_heatmap.json"
  altair-chart-2: "charts/weekday_time_alt.json"
  altair-chart-3: "charts/station_lag_alt.json"
  altair-chart-4: "charts/station_time_heatmap1.json"
folium-loader:
  folium-chart-1: ["charts/foliumChart.html", "500"]
  folium-chart-2: ["charts/line_foliumChart.html", "500"]
toc: true
toc_sticky: true
order:2
---
![NJ_Transit_Amtrak](https://raw.githubusercontent.com/Xiaoyi-Wu0711/nj_transit_model/master/assets/images/us_njtransit_nec.jpeg)


## 1. Stations 
To put the delay in geographical context, we plot the train volume (circle size) and average delay minutes (color) map by different stations in the following interactive map. 
<div id="folium-chart-1"></div>
<br> 
Through this map, we found that **New York Penn Station (NY)**, **Newark Penn Station (NJ)**, **Secaucus Upper Lvl (NJ)**, **Hoboken (NJ)**, **Princeton Junction (NJ)** are the top 5 largest stations in the NJ Transit network by train volume, and they all performed better than the NJ Transit’s average in terms of the average delay minutes (NJ Transit’s average is 5.2min).

Certain stations like Clifton (NJ) and Passaic (NJ) have an average 18-minutes delay of around 1pm, while Denville (NJ) and Philadephia (PA) experienced more than 1-hour severe delay around 1am on average, which is obviously different from other stations.
<div id="altair-chart-1"></div>
<br> 

To better understand the severe delay (>=10min), we also plotted a severity matrix that counts the number of severe delay events by stations and scheduled departure hour. It reveals that New York Penn Station (NY), Newark Penn Station (NJ), Hoboken (NJ), and Secaucus Upper Lvl (NJ) are the stations that have undergone many severe delays throughout the whole day, which might be attributed to the train volume of the busy stations. Although these stations have an acceptable average delay time as the last matrix shows, for example, New York Penn Station’s average delay time during rush hour is only 4 min, given the stations’ massive rider base, the high frequency of severe delay incidents also requires further attention.
<div id="altair-chart-4"></div>
<br> 

## 2. Lines

NJ Transit now operates 11 commuter train lines, largely in northern New Jersey linked to New York City, as well as one route connecting Atlantic City and Philadelphia. They are operated by different divisions and employ a variety of different train types, thus it’s likely that the delay pattern changed according to line.

The following map demonstrates the average delay minutes (circle size) and lines (color) of the station, which shows that the **Atlantic City Line** suffered substantial severe delay compared with all other lines. Each station on the Atlantic City Line has an average delay duration that is four times that of all other stations (which is 4.4 min).

![line_legend](https://raw.githubusercontent.com/Xiaoyi-Wu0711/nj_transit_model/master/assets/images/line_legend.jpg)
<div id="folium-chart-2"></div>

## 3. Station Lag
The following plot shows strong correlation between current station's delay with its last station's delay 30 minutes and 3 hours ago.
Thus, considering the delay propagation effect, we also use previous delay of other stations on the same line in the last three hours and 30 minutes as station lags in our model.
<div id="altair-chart-3"></div>



