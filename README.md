# Ironhack-EDA-Project
### By Alejandro Figueria Ramirez, Bryan Frank, Dylan Sedeno 

# Description 

Ironhack Weeks 5-6 Exploratory Data Analysis Project

[Trello](https://trello.com/invite/b/SkqsBcVP/ATTIa1b54c4c63ebf9afa82c3347aabb234983C0EB9D/the-red-musers)
[Presentation](https://docs.google.com/presentation/d/1NTZg2U_izvyAM4VOe43xKWZlGpBYQjS60Ru1KHkG1Ic/edit?usp=sharing)

# Who are the primary clients who use this online process?

From examining the logons_6_mnth column we see that only clients who logged in at least once in the last six months are considered clients at all.
 
The mean number of logins is 5.57 times a month, with the median being 5, so on average a customer will log on to the service just under once a month. 

<img width="476" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/d275ff81-4b43-48df-9c4d-19535c83a6b2">

A glance at a histogram shows that there isn't an even distribution of user logins, so that won't help us determine what a "typical" customer login rate looks like. 

Information was pulled on those customers who log in at least once every other month, or 3 times every 6 months. It seems from the histogram that customers who log in less frequently are typical.

When comparing the subset with the whole data frame, it seems that there isn't much difference between the two when looking at regular descriptive statistics. This means that the original can be used without much issue. 

## Going solely on the descriptive statistics, it seems that typical* clients are as follows.

- They have been with the company for between 6 and 18 years, or between 70 and 220 months. 
- They are typically between 30 and 60 years old. 
- They have up to 3 accounts. 
- They carry a balance with the company of up to 450,000.
- They've made between 1 and 5 calls in the last six months.
- They've logged on between 2 and 8 times. 

This was determined by looking at the means and standard deviations. 


## Are clients older or younger? 

To answer this question client ages must be analyzed, sorting the ages to age ranges will help to answer these questions.

<img width="188" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/6cdd7849-0c42-40eb-a868-d221583901f2">

<img width="398" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/c2a2fc3e-afe7-4fbe-85a9-a76c5e59ad42">

- From this analysis, we can see that the majority of our clients have had their accounts between the years of 20 and 30. 

- The age range that has the most clients is from 50. the overall client range is from 20 - 60 with outliers in the ranges of 10, 70, 80, and 90

# Visualizations

## Categorical Values 

Variation with process steps as hue:

<img width="446" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/c1a7e209-bdb0-42f5-b023-f9c787b79cae">

Gender Frequency Table:

<img width="428" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/6577e29a-1c34-4513-a42d-f83260cfd98f">

Histogram of client's age:

<img width="443" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/912d7279-8541-40c2-8e32-51ee95991788">

Box plot of client's Age:

<img width="427" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/25c45b68-db45-44c4-9b0b-827b5841415e">

histo plot of client tenure year: 

<img width="440" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/9e17516c-ada9-49d5-818c-5f5375d1d2fe">

Box plot of client tenure year:

<img width="408" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/7df9d8e8-3416-49d4-b14b-896ae4244193">

histo plot of client tenure month: 

<img width="445" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/fd1f5673-d820-49a9-83ba-b999b4b28c3f">

Box plot of client tenure month:

<img width="416" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/1b8160f7-00fd-4838-80f2-905ca2d429ba">

# KPI Analysis

## Completion Rate

One of the main KPIs we decided to investigate was whether or not a statistically significant greater number of clients were able to finish the entire website process in the test or control group. If more people in the control group are able to complete the process in the test group, then the new version of the website should be maintained if completion of the process is desirable. 

As we examined the data we found that many Vanguard clients visited the site and/or worked through the process multiple times. Because of that, we decided to group the visits by visit ID, so we could see the number of *visits* in which a client made it to a certain step. We also wanted to know how far clients progressed through the website process in each visit, so we created a subset that only contains the most recent step a client was on by visit id. In doing so, we have instances in which a process is confirmed multiple times despite a client only reaching that step once.

<img width="449" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/fddef646-7784-42d6-9fb6-d5010e18e96d">

A brief comparison of the results seems to indicate that more clients are able to move from step 3 to confirmation but we want to know if those results are statistically significant or just happenstance. 

In both categories, we had a total of 41,415 clients reached the confirmation step. By just looking at the proportions, we see that 45.77% of clients in the test group made it to the confirmation stage, whereas only 36.92% of the control group made it that far. 

In order to test whether these results are statistically significant, we will run a chi-square test, which will use the control group's rate of reaching the confirmation step as the expected value, and test whether or not the differing results in the test group could be attributed to random chance. 

#### In this case, our hypotheses are as follows:

- H0: There is no difference in the confirmation rates between the control and test groups.
- HA: There is a difference in the confirmation rates between the groups. 

Our null hypothesis is that the changes made to the website were irrelevant, and the differing confirmation rate is just coincidental. Our alternative hypothesis is that the changes made a difference in the confirmation rate. 

Because the p_value is so low, that H0 gotta go. In other words, the p_value indicates that there is virtually no possibility that the differing confirmation rate can be attributed to random chance, so we are forced to conclude that the changes made to the website did statistically impact the rate at which customers complete the online process. If this is desirable, the changes made should be incorporated for all customer interactions going forward. 

## Bounce Rate

The next KPI we decided to test was bounce rate, which is the frequency with which clients visited the site and did not progress past the initial step of the online process. This failure to progress past the initial step can indicate one of two things. The first indication it could give is that the process being presented to the client or visitor is not driving or pushing them to the next step, which would suggest that the layout of the site or process should be adjusted in such a way as to direct them further through the process. The bounce rate could also mean that there is some sort of error or disconnect that needs to be corrected. 

Knowing whether there is a difference in bounce rates between the original site setup and the setup being tested will help us know whether the setup being tested works more efficiently at moving customers through the online process. If the process being tested is more effective in that way, it should be continued. 

To test that difference, we will run another chi-square test to examine the difference (and its statistical significance) between the test and control group. In order to do that, we first need to get a list of clients/visitors who never progressed past the initial phase of the online process.

After collecting a list of visit IDs in which the visitor "bounced," we can use that list to create a new column in our data frame marking those visits that resulted in a "bounce." This indicator column will be treated as a boolean and tested against visit variation, which indicates whether a client was experiencing the test or control process in that visit.  

By just looking at the value counts, we see that about 1/6th, or 12.5% of visits resulted in a bounce, which is fairly alarming. 

When comparing the proportion of bounces in the control versus the test group, we see that the control group experienced a bounce roughly 24% of the time, whereas the test group only experienced bounces 14% of the time. That's a sizeable difference. 

After running a chi-square test, we see that the p-value is incredibly low, leading us to reject our null hypothesis again and conclude that the changes made and tested by the test group have a noticeable and statistically significant impact on bounce rate. If a lower bounce rate is desirable, the updated process should probably replace the current one. 

## Dropoff Rate

This KPI compares whether clients in one of the groups abandoned the process at any steps besides the initial more frequently and whether there is a statistically significant difference in drop-off rates between the test and control groups. If the drop-off rate is higher in the test group, it could signal that the changes made to the process have not simplified the process.

By starting with sorting the data frame, we can more simply pull out the information we need. The cell below sorts the data frame by client ID, visit ID, and date-time, all ascending. 

After sorting the data, we identify the unique process steps that each client reached. Any client that did not make it to the confirm step at least once will be considered a "dropper."

The code above tells us how many clients in each group reached each step at least once. As one would expect, in each group we see that the start group is the largest, and then fewer and fewer clients made it to each succeeding step. The confirm values show how many clients in either group ever made it to the confirm step. The difference between the start and confirm steps in each group tells us how many clients in each group should be considered "droppers." There were 7,732 clients in the control group who never made it to the confirmation step, and there were 7,827 clients in the test group who didn't. That isn't a large difference, but to know if it's significant, we need to test for it. 

Based on this chi-square test, we fail to reject our null hypothesis and conclude that, when it comes to drop-off rates by step, there is no difference between the test group and the control group. Therefore, while the test we ran above shows that there is a significantly different rate of completion in the test group, no individual step's drop-off rate was significantly impacted by the changes made. 

However, using the drop-off rate, we can continue to test whether or not age, tenure, gender, or any other demographic factors affect or impact the drop-off rate, either in general or with each step. 

# Balance

We start by testing whether one Gender trends to carry a higher balance than the other. 

#### Hypothesis 
- H0: mu_bal male = mu_bal female
- H1: mu_bal male != mu_bal female

First, we run a Levene test to test equal variance. We got a low p-value

<img width="440" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/65853169-8f39-4fb6-bb73-ffebd2e632f4">

# MAJOR OBSTACLES 

## CHI Square Test Function Problems

When doing Chi2 tables we had an issue with displaying the chart for c_tenure_drp_ct with our function. it would display the charts for the other charts but not the control data. To combat this a manual chi2 analysis was done on the group

### The Solution

<img width="290" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/3747ab1d-fd71-4d87-bd07-4ef218c42c27">



