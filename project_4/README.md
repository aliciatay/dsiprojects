# Project 4 - West Nile Virus Prediction

## Problem Statement

West Nile Virus (WNV) was first identified in the US in 2001. The following year, Illinois recorded 884  human cases,  67 more than in any other state.

The battle against the West Nile virus is an annual affair Chicago grapples with. Infections can be mild, resulting in flu-like symptoms (West Nile fever [WNF]), or severe, causing paralysis and even death(West Nile neuroinvasive disease [WNND]). Infections can be asymptomatic or symptomatic in humans, with a 4:1 ratio.

This virus poses an immense danger to human life as well as to jobs and economy. Any efforts to mitigate the situation can go a long way in saving lives and livelihoods.

We are a team of Data Scientists at Disease And Treatment Agency, and we aim to collect and analyze data that will help to:

1. Predict the presence of West Nile Virus
2. Understand the main factors that may result in the virus being spread
3. Recommend cost-effective methods to prevent WNV mosquitoes from breeding


## Executive Summary

Our overall Data Analysis Process is carried out in 4 main steps:

#### 1. Exploring and Cleaning of Datasets

The Training Dataset consists of data from 2007, 2009, 2011, 2013. It gives us the weekly recordings of:

    - Trap ID
    - Location details of trap
    - Species and sample size of mosquitoes caught in trap
    - Presence of WNV in caught mosquitoes

The Test Dataset requires us to predict presence of WNV for 2008, 2010, 2012, 2014

The Weather Dataset contains 22 features of weather conditions recorded from 2007 to 2014 from 2 stations: Chicago O’Hare Intl Airport and Chicago Midway Intl Airport.

The Spray Dataset gives us the Date, Time, and Location of spraying efforts done in 2011 and 2013.

We explored and cleaned the data for all four datasets in this section. This includes changing datatypes to the appropriate ones, handling missing data and checking for outliers.

#### 2. Feature Engineering and Exploratory Data Analysis

Here we explore each feature of all the datasets given, and study their correlations to each other as well as to the target variable (WNV Presence). We also study their distributions.

Depending on the analysis, certain features were dropped as we found them to be inconsequential to our study. Feature Engineering was also done where appropriate. Some examples include:

- Grouping together data points with same date and location
- Creating a 'Daylight Minutes' feature by aggregating data from sunset and sunrise timings
- Rolling weather elements into 7 and 14 day averages

#### 3. Modelling of Data to Predict WNV Presence

We first decide what metric to optimise our Data Models on. Due to a large imbalance of the classes within the dataset (95% of data showed absence of virus, and only 5% of the data showed presence of virus), we decided to use ROC-AUC score it is a better [measure of the degree of separability](https://towardsdatascience.com/understanding-auc-roc-curve-68b2303cc9c5).

We carried out multiple models, as well as an extensive Grid Search process to find the best models and modelling parameters. Our results show that the Logistic Regression and SGD Classifier models achieve the best ROC-AUC score. They both achieved a score of approximately 77%, with an approximate Sensitiviity score of 81%.

#### 4. Evaluating Modelling Results

We analyzed the Feature Importances of our best performing models, and these features were identified as Strong Predictors of WNV Presence:   

- Dewpoint  (Rolling 7, 14)
- Wetbulb (Rolling 7, 14)
- Thunderstorm, rain (Rolling 7, 14) (within vicinity as well)
- Airpressure (Stn level, sea level)
- Fog
- Species of mosquitoes

Most predictors give an emphasis on humidity of weather, with rainy weather as an important predictor as well. Warm temperatures do appear to be a factor, but not as strong as we initially thought. August and September appear to be prime months for WNV propagation.


## Conclusions and Recommendations

The estimated cost of life is valued at $9.1 million per citizen. This is, of course, a rather crude estimation as the valye of a human life is not quantifiable. However, we hope that this helps to justify budget spending in government agencies on resources to stop the spread of the WNV Virus.

Based on our analysis results, here are our recommendations

#### 1. Chemical Spraying in areas identified to be at-risk of WNV propogation

Our analysis shows that the current methods of spraying does not seem to be very effective. We propose a re-examination of insecticide spraying: one consideration is oil treatment of stagnant water bodies to kill off larvae.

Our model is also able to detect WNV Presence with an approximate accuracy of 81 percent. We hope that this will help the Chemical Spraying intervention to be more effective in stopping WNV Propogation.


#### 2. Educational/Awareness Campaign

Looking into case studies from countries that have managed to stem mosquito growth, we have found that educating the public on the dangers of mosquito growth is one of the most effective preventive measures.

Simple campaigns that educates citizens to be be more vigilant in clearing stagnant water, especially during hotter and more humid seasons, can go a long way to preventing WNV propagation.These campaigns can also be cost-effective if Community Resources and Networks can be tapped on.


#### 3. Smart Engineering for Water Infrastructure Projects

Another important preventive measure, this can also be very cost-effective and be very valuable in the long-run if successfully carried out. One example is to build drainage infrastructure that prevents water from pooling/stagnating.

This will require communication/understanding between government agencies, but is a proven preventive measure to stem mosquito growth.
