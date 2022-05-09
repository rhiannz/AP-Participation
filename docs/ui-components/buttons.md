---
layout: default
title: Fixed-Effect Regression 
parent: Modeling 
nav_order: 1
---

# Entity-Demeaned Fixed Effect Regression 

Since we are using panel data, we implemented a fixed effect model to determine which of our features can best explain AP Exam particapation rates. More specifically, we used an entity-demean ordinary least squares model, which can be explained as follows:  


![fixed_effect](../../../assets/images/fixed_effect.png)

with ![\beta_k](https://latex.codecogs.com/svg.image?\small&space;\beta_{k}) being the effect on our AP Exam participation rate ![Y_{it}](https://latex.codecogs.com/svg.image?\small&space;Y_{it}) for school ![i](https://latex.codecogs.com/svg.image?\small&space;i) in year 
![t](https://latex.codecogs.com/svg.image?\small&space;t) from a change in ![k](https://latex.codecogs.com/svg.image?\small&space;k)-th feature ![X_{kit}](https://latex.codecogs.com/svg.image?\small&space;X_{kit}) in the same school ![i](https://latex.codecogs.com/svg.image?\small&space;i) and year ![t](https://latex.codecogs.com/svg.image?\small&space;t) such that ![i=1,...,n](https://latex.codecogs.com/svg.image?\small&space;i&space;=&space;1,...,n), ![t=1,...,T](https://latex.codecogs.com/svg.image?\small&space;t=1,...,T), and ![k=1,...,K](https://latex.codecogs.com/svg.image?\small&space;k=1,...,K). 

Therefore, in order to implement this model, we simply subtracted each observation by the school's mean value for that feature across time. This allows us to account for unobservable factor that are school-unique but constant across time and could be affecting our AP Exam participation rates. 
