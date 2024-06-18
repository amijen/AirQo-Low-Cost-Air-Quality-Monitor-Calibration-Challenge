# AirQo-Low-Cost-Air-Quality-Monitor-Calibration-Challenge
## Brief Description 

The objective of this competition is to predict the PM2.5 levels from satellite observations for eight cities in seven different countries in Africa. In fact, particulate matter (PM) includes microscopic matter suspended in air or water. Airborne particles are called aerosols. PM2.5 includes particles less than 2.5 µm in diameter. 

Training and testing datasets have no common cities. The challenge of this competition is to deal with a lot of features that présents also a huge amount of missing values, to extract the necessary informations and add the most suitable features. 

The challenge is part of the [Zindi competition](https://zindi.africa/competitions/airqo-african-air-quality-prediction-challenge).

## Rank on Leaderboard 
Rank: 41/541 
## Our Approach
* **Data Preprocessing** :
  1. Keep only the angles that presents the minimum percentage of missing values and filling with additionnal angles according to [ARKA 360](https://arka360.com/ros/solar-angles/).
  2. Fill the missing values by month period.
* **Feature Engineering** :
  1. Regarding to the fact that the training dataset and testing dataset are coming from different distributions, we noticed that there are multiple sites that are close, so we decide to code the site latitude and site longtitude with geohash encoder.
  2. Adding the variation of PM2.5 by month and by hour
* **Modeling** :
  1. ANN architecture : 4 hidden layers using the AdamW optimizer with 0.05 as a learning rate
  2. Ridge
  3. Combined the two algorithms : $0.0905 y_{-}ann + 0.0975 y_{-}ridge$
