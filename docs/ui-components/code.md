---
layout: default
title: Linear Regressions 
parent: Modeling
nav_order: 2
---

## Feature Selection 

### Backwards Stepwise Linear Regression  

Since many of our features are related to each other, there is quite a bit of multicollinearity presents within our data. Hence, we opted to use a backwards selection instead of a forwards selection to choose our features since it is more suited to dealing with colinearity. 

![backwards_RMSE](../../../assets/images/backwards_RMSE.png) 

Above, we see the 




## Our Chosen Model's Results 


Our best model: 

    AP_oneormore_relative ~ avg_teacher_salary + Pct_Asian + enrl_AP + enrl_AP_science + 
                            enrl_AP_science + students_SAT_ACT + students_chronically_absent 



![backwards_results](../../../assets/images/backwards_results.png)


We can see that there is 
