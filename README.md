# Prediction of Accident Severity


This model uses a UK Department for Transport (DfT) dataset to predict which combination of factors have the most influence on the severity of injury experienced as a result of the accident

## DATA
The data is provided by the UK DfT.  It has been collected by the UK's Police Forces following road traffic accidents during the years 2005 to 2015.

This data is taken from Kaggle. 

It is part of a dataset owned and maintained by the UK's Department for transport.
UK police forces collect data on every vehicle collision in the uk on a form called Stats19. Data from this form ends up at the DfT and is published at https://data.gov.uk/dataset/road-accidents-safety-data.

It is provides as three separate datasets:
Vehicles0515.csv
Casualties0515.csv
Accidents0515.csv

The code merges the three datasets into one and manipulates the data to:
Remove unnecessary fields
Drop NaN values
Focus on the most important features

## MODEL 
This code primarily uses Decision Trees.  It uses this model primarily because it is interpretable and easily visualised.

At the end, The code goes onto explore Random Forests to determine if this improves the accuracy of the model.  In this case, rhe conclusion is that it does not and is not explored further.

## HYPERPARAMETER OPTIMSATION

The codes uses a parameter grid used for hyperparameter tuning.  The following outlines the parameters used and their meanings:

'max_depth: This parameter controls the maximum depth of a tree in the decision tree. It determines how many levels of decisions or splits the tree can have.

'min_samples_split': This parameter sets the minimum number of samples required to split a node further in the tree. If the number of samples in a node is less than this value, no further splitting will occur.

'min_samples_leaf': This parameter specifies the minimum number of samples required in a leaf node, ensuring that each leaf has at least this many samples.

'max_features': This parameter controls the number of features considered when making each split. It can take various values, including:
   - 'auto': considers all features for the split.
   - 'sqrt': considers the square root of the total number of features.
   - 'log2': considers the logarithm base 2 of the total number of features.

The purpose of providing different values is to perform a grid search or hyperparameter tuning. This means that the model is trained and evaluated with different combinations of these hyperparameters.  Eventually, it will find the best set of hyperparameters and return them to the user to use as the preferred set of parameters.  

## RESULTS
This appears to be a robust model that allows for the exploration of data using a range of parameters.  The maximum acuracy approaches 70% which is not sufficient.  The finally settled set of hyperparameters provides an accuracy of 61%.

This model can teach a lot.  The belief is that the dats itself is not necessarily devoid of bias in terms of how the features affect the outcome.  For example, type of vehicle is important but even with sampling, this may be a result of the fact there simply are more cars on the road so therefore more accidents involving cars.

## Building on the model

This model provides a firm base upon which further results can be explored.  For example, it could be better explored with a wider range of data, utilising more of the origiinal features in the dataset.  This does of course come with resource constraints.
