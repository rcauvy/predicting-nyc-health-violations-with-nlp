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

For this project there will be two sources and types of data used:

Historical health and hygiene inspections recorded by New York City Department of Health and Mental Hygiene (DOHMH) public health inspectors
User generated Yelp business ratings and reviews
This project requires data pulled from two different sources, the City of New York and Yelp. To obtain the data we will call the API keys.

The dataset contains every sustained or not yet adjudicated violation citation from every full or special program inspection conducted up to three years prior to the most recent inspection for restaurants and college cafeterias in an active status on the RECORD DATE (date of the data pull). When an inspection results in more than one violation, values for associated fields are repeated for each additional violation record. Establishments are uniquely identified by their CAMIS (record ID) number. Keep in mind that thousands of restaurants start business and go out of business every year; only restaurants in an active status are included in the dataset. Records are also included for each restaurant that has applied for a permit but has not yet been inspected and for inspections resulting in no violations. Establishments with inspection date of 1/1/1900 are new establishments that have not yet received an inspection. Restaurants that received no violations are represented by a single row and coded as having no violations using the ACTION field. Because this dataset is compiled from several large administrative data systems, it contains some illogical values that could be a result of data entry or transfer errors. Data may also be missing. This dataset and the information on the Health Department’s Restaurant Grading website come from the same data source. The Health Department’s Restaurant Grading website is here: http://www1.nyc.gov/site/doh/services/restaurant-grades.page

Why does the Health Department inspect restaurants? The Health Department inspects the approximately 27,000 restaurants in New York City to monitor their compliance with food safety regulations. Inspectors observe how food is prepared, served and stored and whether restaurant workers are practicing good hygiene. They check food temperatures, equipment maintenance and pest control measures.

Since 2010, New York City has required restaurants to post letter grades that correspond to scores received from sanitary inspections. An inspection score of 0 to 13 is an A, 14 to 27 points is a B, and 28 or more points is a C. Grade cards must be posted where they can easily be seen by people passing by.

The New York City Health Department inspects all food service establishments to make sure they meet Health Code requirements, which helps prevent foodborne illness. How often a restaurant is inspected depends on its inspection score. Restaurants that receive a low score on the initial or first inspection in the inspection cycle are inspected less often than those that receive a high score.

The points for a particular violation depend on the health risk it poses to the public. Violations fall into three categories:

A public health hazard, such as failing to keep food at the right temperature, triggers a minimum of 7 points. If the violation can’t be corrected before the inspection ends, the Health Department may close the restaurant until it’s fixed.
A critical violation, for example, serving raw food such as a salad without properly washing it first, carries a minimum of 5 points.
A general violation, such as not properly sanitizing cooking utensils, receives at least 2 points.
Inspectors assign additional points to reflect the extent of the violation. A violation’s condition level can range from 1 (least extensive) to 5 (most extensive). For example, the presence of one contaminated food item is a condition level 1 violation, generating 7 points. Four or more contaminated food items is a condition level 4 violation, resulting in 10 points.

How are restaurants graded? Violations found during inspections carry point values, and a restaurant’s score corresponds to a letter grade. The point/grade cut-offs are the same as for mobile food vending letter grading, with fewer points corresponding to a better grade:

"A" grade: 0 to 13 points for sanitary violations
"B" grade: 14 to 27 points for sanitary violations
"C" grade: 28 or more points for sanitary violations
The City of New York inspects all restaurants cyclically. And if a business does not pass it's initial inspection for the cycle, it will be re-inspected in 3-5 months.