# Business Analytics Manhattan College Competition
Every spring, The O'Malley School of Business hosts the Business Analytics Competition & Conference at Manhattan College (BAC@MC), an exciting opportunity for undergraduate students studying Business Analytics or related fields to test their knowledge and hone their skills.

Competing teams engage in the art and science of decision-making as well as practice their ability to draw business insight from a comprehensive analysis of relevant data. This competition consisted of two rounds with over 90 participants from 24 different colleges. Round one consisted of the participating teams presenting their slides using the supplied data. After the judges decided on their finalists, Round two began which allowed these finalists to revise and update their presentations.

## "Data, Society, Influence" Project Description
In this project, we analyzed global Covid-19 datasets from Bloomberg_ranking, Oxford_covid_government_responses, and Covid_variables_and_country_specific_variables to gain insights from past pandemic and provide recommendations in the event of future pandemic. Due to competition confidentiality, this respository only has final presentation.

## Main analysis
### 1. Story
    - Data Understanding:
      + Oxford dataset: time series data containing 186 countries and regions with variables related to the severity level of government policies in response to each period of the pandemic (e.g: school closing, restrictions on public gathering, etc.)
      + Country specific dataset: time series data containing 225 countries and regions with different variables about the wellbeing of the each country (e.g: diabetes_prevalence, gdp_per_capita, median_age, etc.) and the number of new cases, death, vaccination, etc. 
      + Bloomsberg dataset: ranking of 53 countries based on resilience score (i.e: how the society and the economy were impacted by the pandemic)

    - Data Reliability:
     + 56.81% of the records in Country specific dataset contains missing values and most of them are for small economy countries
     + A lot of important indicators are missing (total_deaths, new_deaths, total_tests, etc.)
     --> Since Covid data was changing rapidly, we could not impute missing values with median or mean values. Also, Bloomsberg dataset was biased since it limits ranking to economies valued more than $200 billion prior to the pandemic 
     --> We should proceed with our analysis with caution since our datasets are not functional 

### 2. Failure: Does our dataset provide practical insights?
####   a.Is there a relationship between the degree of policy implemented and number of new deaths per million?
      - Perform unpaired T-test for two countries which have similar characteristics but did opposite degree of policy severity on average:
         + Null hypothesis: There is no difference in new deaths per million between country did the most policy and the least policy
      --> p values are extremely statistically significant --> reject null hypothesis and conclude that there is substantial difference between 2 countries.
      --> These results are all opposed to common recommendations. 

      --> Why? Because of confounders: there are other external factors that cannot be implied by the data but this is what data gave us. 

       - Perform ANOVA test in worldwide scale:
         + Null hypothesis: There is no difference in total death per million among countries with different policy severity
         + Alternative hypothesis: There is at least one mean of total death per million among different severity levels that is different
      --> Since p-value < 0.0001, the severity level of policy does have an impact on the mean total deaths per million. However, based on test resultsm closures and lockdowns are INEFFECTIVE

####   b. Find another indicator:
        - New case (per million): Inconsisent indicator as testing policy for each country is consistent (more tests might lead to more cases being recorded)
        - New death (per million) (smoothed): There are a lot of abnormal peaks, which might due to correction from previous days 

### 3.Hope
Based on our analysis, we could see that there are some flaws in our dataset. To be more specific, the dataset has missing values, lack of context, recorded inconsistently, and has overgeneralized indicators. 

However, to build a good model, we need a standardized method to record the data so that the data can be more complete, accurate, and continuous. Only in this way, our model can be able to make inferences for the whole population.

So that our group concludes that although we can make models with Covid dataset, we need to be cautious when it comes to reliability and application. 


