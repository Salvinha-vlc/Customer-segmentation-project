# Customer segmentation. A retailer case
*Alberto Abreu & Salvador Rocher*

*Data Analytics, Barcelona August 2019*

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-/-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Organization](#organization)
- [Links](#links)

<a name="project-description"></a>

## Project Description
For the final project we came back to our Business studies roots, and put on the shoes of a newly created consultancy firm driven by data analytics. Our first client (we will call it Tailer for practical purposes) is a retailer concerned by the effectiveness of their current marketing campaigns and its translation to revenues, and they reach to us in seek of answers and advice.

<a name="hypotheses-/-questions"></a>

## Hypotheses / Questions
* Are the current marketing campaigns of Tailer effective in terms of engaging customers to come more often to the stores and driving revenues up? 
* By how much?
* Is it possible to come up with ways to improve those Tailer KPIs?

<a name="dataset"></a>

## Dataset

We got our data from a public web domain called dunnhumby, they claim to be the world's first customer data science platform. In particular the datasets can be found in the following link:

https://www.dunnhumby.com/careers/engineering/sourcefiles?sourcefile=https%3A//www.dunnhumby.com/sites/default/files/sourcefiles/dunnhumby_The-Complete-Journey.zip

The client provided us with raw data that we ended up streamlining and structuring in a simplified way using relational database principles. The simplified outline can be listed as below:

1. Demographics (Household_key - Household_key)
2. Transactions (Household_key - Product_id)
3. Products (Product_id - Product_id)
4. Campaign descriptions (Product_id - Campaign_id)
5. Campaign pools (Campaign_id - Household_key)

Some data key features:

    - 3M transactions over a period of 2 years
    - 2.5k customers
    - >1k products in > 20 departments and > 60 sub departments


<a name="cleaning"></a>

## Cleaning

In the data cleaning part we had to take care of all the tables that were going to be used for our analysis, and that involved, renaming and dropping not needed columns, discretizing categorical variables, creating new calculated columns, checking missing values, removing outliers (using an visual exploratory analysis and then z-scores), re-categorizating values (as in the case of the departments and subdepartments which was creating a lot of noise).

<a name="analysis"></a>

## Analysis

1. First we wanted to check the impact of the marketing campaigns that Tailer had been carrying out. In order to know this, we needed to have the tables streamlined, structured and uploaded into a database. Then, using SQL statements, we were able to assign single purchases to an artificial group where the components were expenditure in euros in products that were subject to a marketing campaign at a particular moment in time and expenditure in euros in products that were not subject to a marketing campaing, Of course, this expenditure could be traced back to the customer carrying out that purchase. In this way, we tested the difference in means of both groups by using a t-test and building a confidence interval with it.

2. The difference in means of the weekly average expenditure of customers that were elegible at a particular time for a particular mk campaign, in products that were part of that campaign respect to the average of the customers that were buying products that were not subject to a mk campaign accros all the time period of study, has proved to be statistically significant.

In particular, the increase in expenditure when carrying out non-customized mk campaigns is 17%, so since literature suggests that targeted/customized mk campaigns can drive expenditure up to 30% in retail industry, it gave us the rationale to explore ways to improve Tailer current performance and mk campaigns effectiveness.

3. In particular, we devised a two-step segmentation using hierarchical and kmeans clustering techniques:

3.1 Macrosegmentation. First we get to know large groups based on their purchase behaviour, which we are able to identify by looking at that purchase behavior and to a certain demographic characteristics like income level, household size, age, or number of kids. 

3.2 Once the macrosegments were identified, we did hypothesis contrasts whether their sensitivity to non-customized campaigns was statistically significant or not, and with this info, along with the purchase behavior, we could acknowledge which of the segments have more potential and hence are strategical and more interesting to build customized mk campaigns around.

3.3 Once the strategical segments have been chosen, we could move on to do another roud of segmentation on those macro groups. In particular, this is called microsegmentation, and helped us to uncover the categories that the members of our strategical groups are more interested in, so that we can individually propose targeted campaigns that are relevant to each particular customers in these groups.

<a name="conclusion"></a>

## Conclusion

* We found evidences to state that most customers seem to be sensitive to mk campaigns.
* We were able to identify strategic customer segments based on their purchase behavior.
* We can drive revenues up by improving customer response to relevant mk campaigns via targeting and microsegmentation.

<a name="future-work"></a>

## Future Work

- Detecting effects of each individual different marketing campaign (store display, emailing, advertisement...).
- Carrying over a market basket analysis for the targeting to not only be based at a product category level but at a more specific product level and suggest cross-selling strategies to drive revenues even further up.

<a name="organization"></a>

## Organization

We used Trello and github. Links can be found below.

<a name="links"></a>

## Links
Include the links to your repository, slides and trello. Feel free to include any other links associated to your project. 

[Repository_1](https://github.com/Salvinha-vlc/Customer-segmentation-project)  
[Repository_2](https://github.com/albertoabreu91/Customer_segmentation_final_project)  
[Slides](https://docs.google.com/presentation/d/1ynlRcykoeSf7IAC4kRVcNKJS3vs4h_EO0UgyR3cwRHk)  
[Trello](https://trello.com/b/asdJQZiT/finalprojecttrello)  
[dbdiagram](https://dbdiagram.io/d/5d598266ced98361d6ddb13c)
