# Predicting the response to flu vaccine

Predicting the immune response of a vaccine in patients is a very as it is associated with predicting the efficacy of the vaccine. It is important to be able to predict this because when a vaccine is administered into a body, there is no guarantee that it will lead to the development of antibodies. And even if it does, there is no guarantee that there will be a development of substantial antibodies. This is because different bodies respond differently to the vaccine, and this can be due to several reasons. And hence, we use the dataset published in this paper: https://www.medrxiv.org/content/10.1101/2021.10.07.21264416v1 , to be able to predict the response of a body to the flu vaccine. 


The dataset consists of ~1300 observations about 700 patients that took the flu vaccine in the given season. It consists of several demographic factors about the patients, their age, health, comorbidities, and the amount of antibodies already present in the body on the day of getting the flu shot. These antibodies are measured before the flu shot is administered. Our field of interest that helps us quantify the immune response to the vaccine is _seroconversion._

To understand seroconversion, let us first understand what does a vaccine contain and what actually happens when a vaccine is administered into the body.


<img src="/flu_vaccine.jpeg" width="250" height="250">


The flu vaccine contains dead/inactivated influenza virus for 4 different strains. Once the vaccine is administered into the body, there are two immune responses. One that generates *B cells* and the other that generates *killer T cells*. B cells further produce antibodies that prevent the virus from entering into our cells. But if a virus does enter the cell, then these antibodies are useless, and killer T cells come into the picture by identifying infected cells and destroying them altogether. Hence, the effectiveness of a vaccine and protection from the disease, both depends on *antibodies* as well as *killer T cells*.  


<img src="/ImmuneResponse.png">




It takes around 3-4 weeks to produce antibodies by the immune system, and hence our dataset records the antibodies present in the patient on Day 0, that is the day of vaccination, before administering the vaccine. And then, on Day 28, which is 28 days after day of vaccination.

<img src="/timeline.png" width="550" height="150">


Where *seroconversion* fits in all this is that it quantifies the increase in antibodies after being given the vaccine. Since, it is the measure of antibodies in the immune system, it is said to have a *correlation* with the efficacy and effectiveness of the vaccine. *Seroconversion* specifically measures the fold rise/increase in the antibodies on Day 28 compared to Day 0, specifically in our dataset. Beyond a certain threshold, the increase in antibodies demonstrates a very high probability of protection from the disease.   
 
Our dataset further groups all those patients that have a *seroconversion* higher than that threshold, and marks them as having *high* seroconversion, and others as having *low*, and those with no increase in antibodies as *none*. However, we are provided with the exact numbers for *seroconversion* as well, for all the 4 individual strains and compositely. 
 
Hence, we state our objective again as, given a dataset with several factors about the patients, we want to predict whether they will have a high seroconversion, indicating higher effectiveness of the vaccine, or a low seroconversion, indicating lower effectiveness of the vaccine, or no seroconversion, indicating zero effectiveness of the vaccine. 


# Looking into the dataset

First, let's explore all the columns that can serve as our target variable. Following are the columns that can be used as our target variables. 
* Seroconversion_H1N1 
* Seroconversion_H3N2 
* Seroconversion_IBV_Yam  
* Seroconversion_IBV_Vic 
* Composite_seroconversion 
* SC_category_H1N1 
* SC_category_H3N2 
* SC_category_IBV_Yam 
* SC_category_IBV_Vic 
* Composite_SC_category 
* Num_SeroPos_strains 
* Baseline_category_Num_SeroPos_strains 
* Composite_baseline 
 
 
We will look into a few of them starting with **seroconversion**, which is referred to as *Composite_seroconversion* in our dataset, and *Composite_SC_category*. *Composite seroconversion* represents the the sum of the seroconversion across all the four strains, and *Composite_SC_category* contains the three categories(high, low, and none), as mentioned above. 

<img src="/Seroconversion.png" width="700" height="350">

We can see that the values for composite seroconversion are right skewed, and that the no. of patients with high seroconversion(>=8.0) are much lesser than the rest of the categories. Using the bar chart for composite seroconversion category, we can see that there is class imbalance as well. 

Moving on, let us see the distribution of seroconversion in patients for each individual strain. 
<img align="left"  src="/Seroconversion_strains.png" width="700" height="600">
<img align="left"  src="/SC_Category_Strains.png" width="650" height="600">





 
