---
layout: default
title: Random Forests 
parent: Modeling
nav_order: 3
---

# Random Forest Modeling 


We saw in the previous section that our linear regression model failed to perform very well. Thus, we decided to explore the usage of a Random Forest Regression in order to try to determine which variables in our model explain AP Exam Enrollment the most. This was done because Random Forest Modeling can be used to account for non-linear relationships between our predictors and response. 

We first ran our random forest with the default parameters, but we found that our model was overfitting quite a bit giving us a testing R² of 0.7 and a training value of around 0.3. So, in order to reduce overfitting we used 10 fold cross-validation with a grid search to determine the optimal parameters that should be used in our random forest regression. We used the negative mean squared error in order to determine the accuracy of our models. Our results from this cross validation grid search were the following: 

<p align="center">
  <img src="../../../assets/images/CV_grid_output.png" width="200" height="75">
</p>


Here we see that even with cross validation and the grid search our model is unfortunetly overfitting. We then attempted to try using gradient boosting trees, but we were unable to make the accuracy of the model increase. We have decided to attribute this issue to our data and the possibiility that we have not included the best predictors to help predict AP Exam Enrollment in different areas. 

In the image below the red line represents the actual y value and the blue line represents the predicted y value. The x-axis is the y value that is being estimated from the model using a fixed effect. 

<p align="center">
<img src="../../../assets/images/accuracy_density.png" width="300" height="450">
</p>

Here we see that the model is having a hard time accounting for the variation on the left and right side, causing there to be a large amount of values to be estimated as zero, or exactly the mean. 

Even though this model performs poorly when trying to predict for a new area, we can say that these features (in the image below) accurately explain the high AP Exam Enrollment in 1/3 of the schools in California. Here we see the feature importance for our random forest model. 

<p align="center">
<img src="../../assets/images/feature_importance.png" width="550" height="650">
</p>
  
Based on the feature importance above we see that `enrl_AP` (the number of students enrolled in an AP course) explains the number of AP exams that will be taken at the school the most. This seems fairly intuitive, but some of the other features that are said to be important are fairly interesting, such as the number of students that take the SAT and ACT, the average teaching salary, and the percent of Asians at a specific school. We were unable to come up with a model that could be generalized to all schools in California, but the insight that we gained from the EDA and modeling still proves to be interesting.
