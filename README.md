# MechaCar Statistical Analysis - AutosRUs

## Overview of Project
A few weeks after starting his new role, Jeremy is approached by upper management about a special project. AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on Jeremy and the data analytics team to review the production data for insights that may help the manufacturing team.

In this challenge, you’ll help Jeremy and the data analytics team do the following:

## Deliverables:
This new assignment consists of three technical analysis deliverables and a proposal for further statistical study. You’ll submit the following:

1. ***Deliverable 1:*** Linear Regression to Predict MPG
2. ***Deliverable 2:*** Summary Statistics on Suspension Coils
3. ***Deliverable 3:*** T-Test on Suspension Coils
4. ***Deliverable 4:*** Design a Study Comparing the MechaCar to the Competition


# Deliverable 1:  
## Linear Regression to Predict MPG

**Statistical Summary:** 

![d1](https://github.com/DataJew/MechaCar_Statistical_Analysis/blob/main/Resources/images/model_summary.png)

**Resulting Model:** 
### mpg =  (6.267)**vehicle_length** + (0.0012)**vehicle_weight** + (0.0688)**spoiler_angle** + (3.546)**ground_clearance** + (-3.411)**AWD** + (-104.0)

From the above output we can see that:

1. The **vehicle length**, and **vehicle ground clearance** are statistically likely to provide non-random amounts of variance to the model; the vehicle length and vehicle ground clearance have a significant impact on miles per gallon on the MechaCar prototype. Conversely,
the **vehicle weight**, **spoiler angle**, and **All Wheel Drive** (AWD) have p-Values that indicate a random amount of variance with the dataset.  

2. The p-Value for this model, ```p-Value: 5.35e-11```, is much smaller than the assumed significance level of 0.05%. This indicates there is sufficient evidence to **reject our null hypothesis, which further indcates that the slope of this linear model is not zero**.

3.  This linear model has an r-squared value of 0.7149, which means that approximately 71% of all mpg predictions will be determined by this model. Relatively speaking, his multiple regression model **does predict mpg of MechaCar prototypes effectively**. 


# Deliverable 2:  
## Summary Statistics on Suspension Coils

First looking at all manufacturing lots:
![d1](https://github.com/DataJew/MechaCar_Statistical_Analysis/blob/main/Resources/images/total_summary.png)


Then each lot individually:
![d1](https://github.com/DataJew/MechaCar_Statistical_Analysis/blob/main/Resources/images/lot_summary.png)


With the understanding that the design specifications for the MechaCar suspension coils mandate that <mark style="background-color: Yellow">**the variance of the suspension coils cannot exceed 100 pounds per square inch (PSI)**</mark> . 

***Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?***

When looking at the entire population of the production lot, the variance of the coils is 62.29 PSI, which is well within the 100 PSI variance requirement.  

Similarly, but significantly more consistent, Lot 1 and Lot 2 are well within the 100 PSI variance requirement; with variances of 0.98 and 7.47 respectively.  However, Lot 3 shows much larger variance in performance and consistency, with a variance of 170.29. This means that Lot 3 is disproportionately causing the variance in the aggregate.  

This boxplot illustrates the differences between the lots:

![d1](https://github.com/DataJew/MechaCar_Statistical_Analysis/blob/main/Resources/images/MechaCar_boxplot.png)


# Deliverable 3:  
## t-Tests on Suspension Coils

The next step is to conduct a t-test on the suspension coil data to determine whether there is a statistical difference between the mean of this provided sample dataset and a hypothesized, potential population dataset. Using the presumed **population mean of 1500**, we find the following:

![d1](https://github.com/DataJew/MechaCar_Statistical_Analysis/blob/main/Resources/images/t-test1.png)

From here we can see the **true mean of the sample is 1498.78**, which we also saw in the summary statistics above.  With a **p-Value of 0.06**, which is higher than the common significance level of 0.05, there is **NOT enough evidence to support rejecting the null hypothesis**; the mean of all three of these manufacturing lots is statistically similar to the presumed population mean of 1500. 

**Next looking at each individual lots:**

![d1](https://github.com/DataJew/MechaCar_Statistical_Analysis/blob/main/Resources/images/t-test2.png)

1. Lot 1 sample actually has the **true sample mean of 1500**, again as we saw in the summary statistics above. With a **p-Value of 1**, clearly we cannot reject (i.e. accept) the null hypothesis that there is no statistical difference between the observed sample mean and the presumed population mean (1500).
2. Lot 2 has essentially the same outcome with a **sample mean of 1500.02**, a **p-Value of 0.61**; the null hypothesis cannot be rejected, and the sample mean and the population mean of 1500 are statistically similar.
3. However, in Lot 3, **the sample mean is 1496.14** and the **p-Value is 0.04**, which is lower than the common significance level of 0.05.  All indicating to **reject the null hypothesis** that this sample mean and the presumed population mean are **not statistically different**.

The production process in Lot 3 needs to be checked for system fails and the suspension coils from this lot need to be inspected to remove those not meeting quality criteria.

# Deliverable 4:  
## Study Design: MechaCar vs Competition

This study would involve collecting data on MechaCar and its comparable models across several different manufacturers over the last 3 years.

* What are the competitions' comparable models, 
* Which cars will MechaCar be competing with head-to-head? which cars will be included in the study?
* Which factors will look at the study to determine the relevant to selling price?
 

#### Metrics
Collecting data for comparable models across all major manufacturers for past 3 years for the following metrics:


*  Current Price (Selling) **[Dependent Variable]**
*  Safety Feature Rating 
*  Drive Package
*  Engine (Electric, Hybrid, Gasoline / Conventional)
*  Resale Value
*  Average Annual Cost of ownership (Maintenance)
*  MPG (Gasoline Efficiency)

#### Hypothesis: Null and Alternative
After determining which factors are key for the MechaCar's genre:

 * Null Hypothesis: MechaCar is priced correctly based on its performance of key factors for its genre.
 * Alternative Hypothesis: MechaCar is NOT priced correctly based on performance of key factors for its genre.
 
#### Statistical Tests
A **multiple linear regression** would be used to determine the factors that have the highest correlation/predictability with the list selling price (dependent variable); which combination has the greatest impact on price.
