---
layout: default
title: Random Forests 
parent: Modeling
nav_order: 3
---

# Random Forest Modeling 


We saw in the previous section that our linear regression model failed to perform very well. Thus, we decided to explore the usage of a Random Forest Regression in order to try to determine which variables in our model explain AP Exam enrollment the most. This was done because Random Forest Modeling can be used to account for non-linear relationships between our predictors and response variable. 

We first ran our random forest with the default parameters, but we found that our model was overfitting quite a bit giving us a testing R² of 0.7 and a training R² of around 0.3. So, in order to reduce overfitting we used 10-fold cross-validation with a grid search to determine the optimal parameters that should be used in our random forest regression. We used the negative mean squared error in order to determine the accuracy of our models. Our results from this cross validation grid search were the following: 

<p align="center">
  <img src="../../../assets/images/CV_grid_output.png" width="250" height="125">
</p>


Here we see that even with cross validation and the grid search, our model is unfortunetly overfitting. We then attempted to use gradient boosting trees, but we were unable to make the accuracy of the model increase. This may be attributed to our data and the possibiility that we have not included the best predictors to help predict AP Exam Enrollment in different areas. 

In the image below, the red line represents the actual y-value and the blue line represents the predicted y-value. The x-axis represents the entity-demeaned y-values of our data after being transformed for our fixed effect model. 

<p align="center">
<img src="../../../assets/images/accuracy_density.png" width="300" height="450">
</p>

Here we see that the model is having a hard time accounting for the variation on the left and right side, causing there to be a large amount of values to be estimated as zero, or exactly the mean. 

Even though this model fails to generalize to all schools, we can say that the features below are able to accurately explain up to 70% of the variation in AP Exam enrollment for 1/3 of the schools in California. Here we see the feature importance for our random forest model:

<p align="center">
<img src="../../../assets/images/feature_importance.png" width="550" height="650">
</p>
  
Based on the feature importance above, we see that `enrl_AP` (the % of students enrolled in an AP course) explains AP exam participation rates the most. This seems fairly intuitive, but some of the other features that are important are fairly interesting as well, such as the percentage of students that take the SAT and ACT, the average teaching salary, and the percent of Asian students at a specific school. We were unable to come up with a model that could generalize to all schools in California, but the insight that we gained from our EDA and modeling still proves to be insightful.
