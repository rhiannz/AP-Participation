---
layout: default
title: Linear Regressions 
parent: Modeling
nav_order: 2
---

## Feature Selection 

### Backward Stepwise Linear Regression  

Since many of our features are related to each other, there is quite a bit of multicollinearity present within our data. Hence, we opted to use a backward selection instead of a forward selection to choose our features since it is more suited to dealing with colinearity. 

We utilized 5-fold cross-validation in addition to our entity-demeaned OLS model to first determine the number of features we should include in our final model. We then observed the changes occurring between the average training and testing RMSE of our cross-validations as we increased the number of features in our model.  

![backwards_RMSE](../../../assets/images/backwards_RMSE.png) 

We can see that when we have 7 features in our model, not only does our testing RMSE reach its minimum but our training RMSE also begins decreasing more gradually after this point. Hence, we began exploring which 7 features had been chosen in each of our cross-validated models. However, after considering these individual models' adjusted R-squared scores, p-values, and which features they have in common, we decided to use the following 6-feature model:  

    AP_oneormore_relative ~ avg_teacher_salary + Pct_Asian + enrl_AP + enrl_AP_science + 
                            enrl_AP_science + students_SAT_ACT + students_chronically_absent 


## Our Chosen Model's Results 

![backwards_results](../../../assets/images/backwards_results.png)

We selected this model in order to minimize our training and testing RMSE while keeping our adjusted R-squared score as high as possible, thereby maximizing both the accuracy and overall explanatory power of our model.  Most notably, all of the features included are significant at a 0.10 level. 

Of course, we realize that there is still room for improvement since our adjusted R-squared score is rather low. Hence, we will be exploring non-linear models in the next section. 
