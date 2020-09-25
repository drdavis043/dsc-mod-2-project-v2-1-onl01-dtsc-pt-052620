
# King County Housing Analysis


## Contributing Members:

Joe Sanders, Attila Gogos, Derek Davis

## Project Overview

The first King Count "Link" Light Rail stations opened in 2009. Since 2008, residents of King Count have voted to expand Link Light Rail twice, despite the fact that each vote has had significant impact on real estate taxes. As King County prepares to vote on a third Light Rail Expansion initiative, we sought to answer the question: Does having access to Link increase what a home can sell for and if not what drives this price?

## Data Exploration and Cleaning

Our first step was to import, explore, clean and combine the following datasets. One of which was provided by the flatiron school and the other two imported to improve analysis.

### King County Housing Data Set (2015)
*Provided by flatiron school

### 2015 to 2019 Price Data Trend
*Imported from metrostudy.com's housing reports available to real estate professionals.

### Link Light Rail Dataset
*Manually gathered link of Light Rail locations by zip code.

## Assumptions

After we coerced the data into one clean dataframe we checked for a normal distribution and a linear correlation of each variable to the Estimated 2020 Price. Below are the variables that fit our assumptions and although the presence of link alone was not an initial predictor we will later consider tranformations and interactions to further examine this possibility.

![Bedrooms](images/Bedrooms.png)

![Bathrooms](images/Bathrooms.png)

![sqft_above](images/sqft_above.png)

![sqft_living](images/sqft_living.png)

![sqft_living15](images/sqft_living15.png)

![grade](images/grade.png)

### Assumption Model

Our initial model generated a R-Squared value of .505

![Assumption_Model](images/Assumption_Model.png)

## Model Refinement

We combined certain features to reduce their redundant impact (multicollinearity).
   *sqft_living_mc: sqft_living x sqft_above x sqft_living15
   *sqft_lot_mc: sqft_lot x sqft_lot15

In addition to addressing multicollinearity we used the interactions of several others variables to make three additional features.
   *Rooms: Bedrooms x Bathrooms
   *Density: sqft_living x sqft_lot x floors
   *Link Score: link_announced + link_construction_started + link_open_nearby
   
Finally because we had a high number of features that were not regularly distributed, we used logarithmic transformation to create additional features, and then analyzed the correlations between all measures.

![Corrmap](images/Corrmap.png)

## The Adapted Model

Our next model generated a significantly higher R-Squared value of .645, but we believe further utilization of our log transformations will increase it even further.

![Model1](images/Model1.png)

## The Logarithmic Model

Our final model produced an even higher R-Squared value of .757 a drastic improvement from our assumptive model and even our adapted model.

![Final_Model](images/Final_Model.png)

## Future Considerations

We have established a great and telling set of varibles for a reliability sufficient model. However, there are surely other variables that could be considered if we were to decide to move forward with this real estate opportunity. We have already incorporated into the model the impact that the Link rail service has on the housing market. We believe that ease of transportation has a major impact and with that we would investigate additional travel means. Below are a few future considerations that we would like to suggest.

### Does access to buses have an impact on housing prices?
*Resource to utilize: King County Metro Maps

### Does "Bike-Ability" have an impact on housing prices?
*Resources to utilize: Elevation Data, Topograhpy Maps

### Does "Walkability" have an impact on housing prices?
*Resources to utilize: Walkability Score, Distance to Nearest Essential Services

   
   
   
   
   
   




