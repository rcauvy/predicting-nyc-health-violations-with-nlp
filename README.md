# Predicting NYC Health Violations

Using Yelp reviews and the city's open data of past violations to flag public health risks at NYC restaurants.

![Kitchen](images/Food-Safety-Introduction.jpeg)

## Introduction

Cities across the United States are capitalizing on data. Predictive modeling is becoming a prominent tool for public safety in many cities where the local authority can target interventions. These preventative measures range from predicting which landlords are not complying with city ordinances to which buildings pose the highest risk of fire so they can send inspectors out and prevent an outbreak before it happens.

According to the CDC, more than 48 million Americans per year become sick from food, and an estimated 75% of the outbreaks came from food prepared by caterers, delis, and restaurants. In most cities, health inspections are generally random, which can increase time spent on spot checks at clean restaurants that have been following the rules closely — and missed opportunities to improve health and hygiene at places with more pressing food safety issues.

### Objective

The goal for this project is to leverage public citizen generated data from social media to narrow the search for critical health and safety violations in New York City. As the City of New York manages an open data portal, everyone can access historical hygiene inspections and violation records. By combine these two data source this project aims to determine which words, phrases, ratings, and patterns among restaurants lead to critical health and safety violations. This model can assist city health inspectors do their job better by prioritizing the kitchens most likely to be in violation of code.

The New York Health Department inspects the approximately 27,000 restaurants within the city to monitor their compliance with food safety regulations. Inspectors observe how food is prepared, served and stored and whether restaurant workers are practicing good hygiene. They check food temperatures, equipment maintenance and pest control measures.

## The Data

This project utilises 3 data sources:
* Historical health and hygiene inspections recorded by New York City Department of Health and Mental Hygiene (DOHMH) public health inspectors
* Yelp API business data and ratings 
* Yelp user generateda reviews




### New York Open Data

Since 2010, New York City has required restaurants to post letter grades that correspond to scores received from sanitary inspections.Since 2010, New York City has required restaurants to post letter grades that correspond to scores received from sanitary inspections.

"A" grade: 0 to 13 points for sanitary violations
"B" grade: 14 to 27 points for sanitary violations
"C" grade: 28 or more points for sanitary violations


This dataset and the information on the Health Department’s Restaurant Grading website come from the same data source. The Health Department’s Restaurant Grading website is here: http://www1.nyc.gov/site/doh/services/restaurant-grades.page

The dataset used in this project can be viewed and downloaded  here:

https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j

Detailed descriptions about each column can be found in the Restaurant Inspection Data Dictionary.

### Yelp Business Data

You can sign up for access and obtain credentials to the Yelp API here: 
https://www.yelp.com/developers/documentation/v3

We call the Yelp API at the Phone Search Endpoint for all the numbers in the phone_numbers list tht correspond to the businesses from the NYC dataset to gather details about each indivdual business such as their ratings and Yelp page urls. 
However the API only allows 5000 callers per day so we'll slice the list into smaller list.


### Yelp Review Data

Now that all the restaurants from the NYC DOHMH dataset have been used to search the Yelp API and have been concatenated we can use the return url to gather reviews for each business using BeautifulSoup to web scrape the text from the front page of each businesses Yelp site.


### Joining The Data
After gather all the data, removing duplicates and dropping restaurants without reviews, we are left with 13,061 unique businesses


## Exploring The Dataset


![Map](images/restaurant_map.png)

![Features](images/target_v_features.png)


### Exploring The Text Data
![Text_Freq](images/freq_text.png)
![Positive Wordcloud](images/neg_wc.png)
![Negative Wordcloud](images/pos_wc.png)


## NLP Modeling

### Bag-Of-Words

#### Count Vectorizer

#### Tdf_idf

### Deep NLP

#### Word2Vec
#### Pretrained gloVe

