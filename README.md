# Ironhack-EDA-Project
### By Alejandro Figueria Ramirez, Bryan Frank, Dylan Sedeno 

# Description 

Ironhack Weeks 5-6 Exploratory Data Analysis Project

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

<img width="190" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/6cdd7849-0c42-40eb-a868-d221583901f2">

<img width="398" alt="image" src="https://github.com/DmanDSR/Ironhack-EDA-Project/assets/48893423/c2a2fc3e-afe7-4fbe-85a9-a76c5e59ad42">

- From this analysis, we can see that the majority of our clients have had their accounts between the years of 20 and 30. 

- The age range that has the most clients is from 50. the overall client range is from 20 - 60 with outliers in the ranges of 10, 70, 80, and 90


