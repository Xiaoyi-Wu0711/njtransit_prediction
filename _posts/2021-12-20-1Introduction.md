---
title: "Introduction & Background"
date: 2021-12-20
categories:
  - blog
tags:
  - Github Page
  - update
excerpt: "Inspiration of the project."
order:1
---

![NJ_Transit_Amtrak](https://raw.githubusercontent.com/Xiaoyi-Wu0711/nj_transit_model/master/assets/images/us_njtransit_nec.jpeg)




## 1. Inspiration

This project aims to analyze the spatio-temporal distribution of train delay in New Jersey Transit(NJ Transit), and 
make a binary prediction model to predict if certain train at specific station is going to experience a delay more than 10 minutes. 

Covering a service area of 5,325 square miles, NJ Transit is the third-largest statewide public transportation system in the United States, operating bus, light rail, and commuter rail. It also has the nation’s second-largest commuter rail network which has 11 lines, 164 rail stations and serves over 300,000 customers everyday. The commuter rail network are concentrated in northern New Jersey, despite the Atlantic City Line runs between Atlantic City and Philadelphia and is detached from the main network. 

However, the rail network has been plagued by chronic delay issues for a long time. According to the [data](https://www.transit.dot.gov/2018-breakdowns) released by Federal Transit Administration, NJ Transit have the most commuter train breakdown in 2018. 

Thus, we conduct analysis to reveal factors which influence delay and help the operators provide more punctual services. 

At the same time, we develop prediction models to forecast when and where the delay will occur to help the passengers mitigate delay cost.  

![NJ_Transit_Amtrak](https://raw.githubusercontent.com/Xiaoyi-Wu0711/nj_transit_model/master/assets/images/penn-station-delays.jpeg)
Delay in NYC Penn Station on Feb.3, 2020 <a href="https://pix11.com/news/local-news/manhattan/nearly-3-hour-delays-massive-crowds-continue-at-penn-station/">(Smith, 2020)</a>
 
# 2. Data Preparation

We use the open NJ Transit origin-destination performance data from NJ Transit and Amtrak train trips
 on [Kaggle](https://www.kaggle.com/pranavbadami/nj-transit-amtrak-nec-performance?select=2018_11.csv) as the main dataset. Here we select historical data from 11/2019 to 12/2019, totaling 682,163 observation as the training and testing data. 

To clean the data, we dropped any rows with NA values in the `scheduled_time`, `delay_minutes`, `from_id`, `to_id` columns. Additionally, in order to focus on the issue of punctuality, we drop data labelled as `cancelation`. 

Also, we use the weather station data from [National Centers for Environmental Information](https://www.ncdc.noaa.gov/cdo-web/search?datasetid=GHCND) to include the weather conditions into our prediction model. 15% percent of observation values in this datasets are NA. Here, we fill the NA values of binary variables such as `fog` and `precipitation` with 0, and that of continuous variables such as `temperature` with mean value.


## 3. Content
The project will be seperated into following 2 sections:
- **Exploratory Analysis**: <a href="https://xiaoyi-wu0711.github.io/nj_transit_model/3when_delay/">when</a>, <a href="https://xiaoyi-wu0711.github.io/nj_transit_model/2where_delay/">where</a>  did the delay usually happen?

- **Modeling**:  <a href="https://xiaoyi-wu0711.github.io/nj_transit_model/1model/">methods</a> involving feature engineering, model selection, cross-validation. 

  

