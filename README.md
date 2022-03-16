# Predicting the response to flu vaccine

Predicting the immune response of a vaccine in patients is a very as it is associated with predicting the efficacy of the vaccine. It is important to be able to predict this because when a vaccine is administered into a body, there is no guarantee that it will lead to the development of antibodies. And even if it does, there is no guarantee that there will be a development of substantial antibodies. This is because different bodies respond differently to the vaccine, and this can be due to several reasons. And hence, we use the dataset published in this paper: https://www.medrxiv.org/content/10.1101/2021.10.07.21264416v1 , to be able to predict the response of a body to the flu vaccine. 


The dataset consists of ~1300 observations about 700 patients that took the flu vaccine in the given season. It consists of several demographic factors about the patients, their age, health, comorbidities, and the amount of antibodies already present in the body on the day of getting the flu shot. These antibodies are measured before the flu shot is administered. Our field of interest that helps us quantify the immune response to the vaccine is _seroconversion._

To understand seroconversion, let us first understand what does a vaccine contain and what actually happens when a vaccine is administered into the body.


<img src="/flu_vaccine.jpeg" width="250" height="250">


The flu vaccine contains dead/inactivated influenza virus for 4 different strains. Once the vaccine is administered into the body, there are two immune responses. One that generates *B cells* and the other that generates *killer T cells*. B cells further produce antibodies that prevent the virus from entering into our cells. But if a virus does enter the cell, then these antibodies are useless, and killer T cells come into the picture by identifying infected cells and destroying them altogether. Hence, the effectiveness of a vaccine and protection from the disease, both depends on *antibodies* as well as *killer T cells*.  


<img src="/ImmuneResponse.png">




It takes around 3-4 weeks to produce antibodies by the immune system, and hence our dataset records the antibodies present in the patient on Day 0, that is the day of vaccination, before administering the vaccine. And then, on Day 28, which is 28 days after day of vaccination.

<img src="/timeline.png" width="550" height="150">



