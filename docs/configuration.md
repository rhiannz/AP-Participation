---
layout: default
title: Data Collection & Cleaning
nav_order: 2
---

# Data Collection & Cleaning 

## Data Collection 

We began by collecting our data from the Urban Institute Education Data Portal.<sup>[4]</sup>  Their goal is to compile a multitude of different datasets from different schools, school districts, and colleges and have all the information available and readily accessible. Our goal for this project was to analyze which factors influence AP Exam enrollment. We chose to specifically look at data for schools in California. We gathered 9 different datasets from the National Center for Education Statistics’ Common Core of Data (CCD) and from the Civil Rights Data Collection (CRDC). The different datasets that we read in were on the following topics:

- AP Exams  (specifically looking at students who took one or more AP Exam) 
- School Directory
- School Enrollment  
- Discipline 
- Chronic Absenteeism  
- SAT & ACT Participation 
- Teachers and Staff
- School Finance 
- AP, IB, and GT Enrollment 

Our main focus was on the table that contained AP Examination data as this is our main variable in question. With the other 8 datasets we had a large number of different variables once they where compiled together. 

## Data Cleaning and Bias 

We read in the 9 different datasets using API’s. Once this was done we subsetted the data specifically for California. We then merged the 9 different datasets together. Once this was done there were many missing values in our data that had to be accounted for. Below we see what the merged data looks like before we cleaned it (this is only some of the variables that we actually had). 

![missing_no_unclean](../../assets/images/missing_no_unclean.png) 

It should be noted that there were some schools in California that did not report their AP Exam enrollment. For the sake of our analysis and modeling we removed these NA values, leaving us with about a ⅓ of the total Californian schools. We acknowledge that this may introduce a bias. We explored what type of schools may be more likely to report their AP Exam enrollment and we found that the schools that tend to report these numbers are usually from the following categories: 

- They have a higher total salary for all employees 
- Generally they are larger schools 
- These schools tend to have higher rates of SAT & ACT student participation 


We then cleaned our data set. It should be noted that during out data cleaning process we found multiple discrepancies in the values reported across the different data sets. We adjusted these numbers in order to make them computationally viable. However, these altered values may not reflect reality and may possibly impact our future analysis. 

Since our goal was to determine which factors influenced AP Examination enrollment and we had a significant amount of variables, we decided it was necessary to drop some columns that were insignificant. We used a correlation matrix and removed variables that had a correlation between -0.1 and 0.1. Finally, we imputed the missing observations. As we can see, the number of rows in our final matrix significantly decreased compared to the matrix above. This is because the data was collected for each individual race and sex at these schools. So, in order to reduce the number of columns and easily conduct analysis, we created new columns for these demographics allowing us to significantly reduce the size of our dataframe. We then end up with the following clean dataframe:  

![msno_complete](../../assets/images/msno_complete.png) 

*Clarifying Ambiguous Variable Names*

| Variable Name        | Description   | 
| ------------- |:-------------:| 
| `ncessch`      | school ID number | 
| `students_AP_exam_none`      | number of students that didn't take any AP Exams     |   
| `students_AP_exam_oneormore` | number of students that took at least one AP Exam     | 
|`latitude` | the latitude of the school|
|`longitude`| the longitude of the school | 
| `enrollment` | the number of students enrolled in the school |
|`school_name` | the name of the school |
|`AP_oneormore_relative`      | % of students that took an AP Exam at the school |
|`teachers_per_student` | number of teachers per student | 
|`security_guards_per_students` | number of security guards per student | 
|`avg_teacher_salary` | average teacher salary |
| `%Asian` | % of Asian students|
|`%Black` | % of Black students|
|`%Hispanic` | % of Hispanic students|
|`%Indigenous American`| % of Indigenous American students|
|`%Multiracial` | % of Multiracial students|
|`%Pacific Islander` | % of Pacific Islander students| 
|`%White` | % of White students |
|`%Female`| % of Female students|
|`%Male`| % of Male students|
|`enrl_AP` | % of students enrolled in AP classes |
|`enrl_AP_science` | % of students enrolled in AP science classes |
|`enrl_AP_math` | % of students enrolled in AP math classes |
|`enrl_AP_other` | % of students enrolled in other AP classes |
|`enrl_gifted_talented` | % of students enrolled in gifted and talented programs |
|`students_SAT_ACT` | % of students who took the SAT or ACT |
|`students_chronically_absent` | % of students who are chronically absent |
|`students_report_harass_dis` | % of students harassed or bullied on the basis of disability|
|`students_susp_in_school`| % of students who received one or more in-school suspensions|
|`students_susp_out_sch_single` | % of students who received an out-of-school suspension|
|`students_susp_out_sch_multiple` | % of students who recieved multiple out-of-school suspensions|
|`students_arrested` | % of students arrested |
|`avg_teacher_salary_1K` | average teacher salary in thousands| 




