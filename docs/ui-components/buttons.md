---
layout: default
title: Fixed-Effects Model 
parent: Modeling 
nav_order: 1
---

# Entity-Demeaned Fixed Effect Regression 

Since we are using panel data, we implemented a fixed effect model to determine which of our features can best explain AP Exam participation rates. More specifically, we used an entity-demean ordinary least squares model, which can be explained as follows:


![fixed_effect](../../../assets/images/fixed_effect.png)

such that ![Y_{it}](https://latex.codecogs.com/svg.image?\small&space;Y_{it}) is the AP Exam participation rate of school ![i](https://latex.codecogs.com/svg.image?\small&space;i) in year ![t](https://latex.codecogs.com/svg.image?\small&space;t) and ![X_{kit}](https://latex.codecogs.com/svg.image?\small&space;X_{kit}) is the ![k](https://latex.codecogs.com/svg.image?\small&space;k)-th feature of the same school ![i](https://latex.codecogs.com/svg.image?\small&space;i) in year ![t](https://latex.codecogs.com/svg.image?\small&space;t). ![\beta_k](https://latex.codecogs.com/svg.image?\small&space;\beta_{k}) is the effect on AP Exam participation rates caused by the ![k](https://latex.codecogs.com/svg.image?\small&space;k)-th feature ![X_{kit}](https://latex.codecogs.com/svg.image?\small&space;X_{kit}). 
Additionally, ![i=1,...,n](https://latex.codecogs.com/svg.image?\small&space;i&space;=&space;1,...,n), ![t=1,...,T](https://latex.codecogs.com/svg.image?\small&space;t=1,...,T), and ![k=1,...,K](https://latex.codecogs.com/svg.image?\small&space;k=1,...,K). 

Therefore, in order to implement this model, we simply subtracted each observation by the school's mean value for that feature across time. This allows us to account for unobservable factors that are school-unique but constant across time and could be affecting our AP Exam participation rates.
