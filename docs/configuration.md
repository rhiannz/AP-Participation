---
layout: default
title: Data Collection & Cleaning
nav_order: 2
---

# Data Collection & Cleaning 

## Data Collection 

We began by collecting our data from the Urban Institute Education Data Portal. Their goal is to compile a multitude of different datasets from different schools, school districts, and colleges and have them available in one spot. Since our goal for this project  was to analyze which factors influence AP Exam Enrollment we looked at data for specific schools in California. We gathered 9 different datasets from the National Center for Education Statistics’ Common Core of Data (CCD) and from the Civil Rights Data Collection (CRDC). The different datasets that we read in were on the following topics:

- AP Exams  (specifically looking at students who took one of more AP Exam) 
- School Directory
- School Enrollment  
- Discipline 
- Chronic Absentee 
- SAT & ACT Participation 
- Teachers and Staff
- School Finance 
- AP, IB, and GT Enrollment 

Our main focus was on the table that contained AP Examination data as this is our main variable in question. With the other 8 datasets we had a total of 40 different variables once they where compiled together. 

## Data Cleaning and Bias 

We read in the 8 different datasets using API’s. Once this was done we subsetted the data to be specifically for California. We then merged the 8 different datasets together. Once this was done there were many missing values in our data that had to be accounted for. Below we see what the merged data looks like before we cleaned it (this is only some of the variables that we actually had). 

![missing_no_unclean](../../assets/images/missing_no_unclean.png) 

It should be noted that there were some schools in California that did not report their AP Exam enrollment. For the sake of our analysis and modeling we removed these NA values giving us about ⅓ of the total California schools. We acknowledge that this may introduce a bias. We explored what type of specific schools may be more likely to report their AP Exam Enrollment and we found that the schools that tend to report these numbers are usually from the following category: 

- They have a higher total salary for all the workers. 
- Generally they are larger schools 
- These schools tend to have higher rates of SAT & ACT student participation 




*Rhiann talks about the cleaning of the data set* 

Then after imputing some missing observations and dropping repetitive columns, we created ended up with a nice, clean dataframe, as seen below.  
![msno_complete](../../assets/images/msno_complete.png) 



