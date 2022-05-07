---
layout: default
title: Fixed-Effect Regression 
parent: Modeling 
nav_order: 1
---

# Entity-Demeaned Fixed Effect Regression 

Since we have panel data, we utilized a fixed effect model to determine which of our features can best explain AP Exam particapation rates. More specifically, we used an entity-demean ordinary least squares model, which can be explained as follows:  


![fixed_effect](../../../assets/images/fixed_effect.png)

with $\beta_k$ being the effect on our AP Exam participation rate $Y_it$ ![img]http://www.sciweavers.org/tex2img.php?eq=Y_%7Bit%7D%20&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0[/img] for school $$i$$ in year t from a change in k-th feature X_kit in the same school i and year t such that i = 1, ..., n, t = 1, ..., T, and k=1,...,K. 

Therefore, in order to implement this model, we simply subtracted each observation by the school's mean value for that feature across time. This allows us to account for unobservable factor that are school-unique but constant across time and could be affecting our AP Exam participation rates. 
