---
layout: default
title: Exploratory Data Analysis 
nav_order: 3
---

# Exploratory Data Analysis 

### Correlation Matrix of our Cleaned Dataset 

![completed_correlation](../../assets/images/completed_correlation.png)

(Note: `AP_oneormore_relative` is the percent of students who took one or more AP Exam while `students_AP_exam_oneormore` is the number of student who took one or more AP Exam ) 


Here we can see the correlation matrix of our completed data. We can see how AP Exam Participation (denoted as AP_oneormore_relative) is most positively correlated with other AP related features, such as as enrollment in AP courses, which makes sense intuitively. AP Exam participation is also positively correlated with enrollment in the gifted/talented programs and SAT/ACT participation, which we should expect as well since students who take AP Exams are likely to take other tests and be a part of other academically rigorous programs. AP Exam participation is negatively correlated with features concerning student suspensions and absenteeism. This is something we should also expect, as schools with higher rates of student misconduct will likely have lower academic performance. We should also note that AP Exam participation is most strongly correlated with Asian student population, which we will be exploring next. 



### AP Exam Participation Percentages by Race and Year  

![PctParticipation](../../assets/images/PctParticipation.png)

Above, we can see the average AP Exam participation rates by race and year. Most notably, Asian students have the highest AP Exam participation rates, by far. However, when looking at the rest of the student body, there are rather similar partipation rates across racial groups. We should also note that there is a general increase in exam participation throughout the years. 

### School Population by Race and Year 

![PctPop](../../assets/images/PctPop.png)

After observing the exam particpation rates, we look at school populations by race and year. Now comparing these two bar charts, we can clearly see stark contrast between the exam particpation rates and the student populations. Student population is not nearly as evenly distributed across racial groups as exam particpation rates are. For example, Hispanic and Indigenous Anerican students had similar exam participation rates even though they have the largest difference in population. Additionally, Asian students have the highest exam participation rates while they are not even close to being the majority in terms of population. It is quite interesting to note the similar percentages in AP Exam participation despite there being so much variation in student population. 

 
### Student Participation in Advanced Academic Programs 

![ap_boxplots](../../assets/images/ap_boxplots.png)

Here is a quick glance of AP Exam enrollment in relation to student partication in other advanced academic programs. We can see how these other features have distributions that are quite similar to AP Exam participation. As mentioned above, this is to be expected since we would presume that students who are taking AP exams are enrolled in at least one AP course and that these AP students very likely to be engaged in other acadmically rigourous activites as well. And of course, student enrollment in AP science courses and AP math courses have the smallest range since these students are a subset of those who are taking AP courses in general.


### Student Misbehavior and Disciplinary Actions 

![discipline_boxplots](../../assets/images/discipline_boxplots.png)


We can see that the distibutions of the features concerning student misbehavior and disciplinary action are much smaller than the distribution of AP Exam participation, which is good news since we would hope that less students are being suspended or arrested. 

We must also note the unexpectedly large range of the boxplot detailing the percent of chronically absent students. This is most likely due to the inconsistencies found throughout our data, as mentioned in the previous "Data Collection & Cleaning" section. These discrepancies may be affecting our other exploratory data visualizations and our future modeling as well. 
