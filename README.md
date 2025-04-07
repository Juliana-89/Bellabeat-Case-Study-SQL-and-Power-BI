# Bellabeat-Case-Study

## 📝 Introduction 

The **BellaBeat Case Study** is a capstone project for the **Google Data Analytics Professional Certificate** on Coursera. In this case study, I will perform various real-world tasks of a junior data analyst at a fictional company called Bella Beat. Ask, prepare, process, analyze, share, and act are the stages of the data analysis process that I will use to solve the key business problems.

## 💬 Background

Urška Sršen and Sando Mur co-founded Bellabeat, a tech company specializing in smart health products designed for women. By gathering insights on activity, sleep, stress, and reproductive health, Bellabeat helps women better understand their well-being and daily habits. Established in 2013, the company has expanded quickly, becoming a leader in women's wellness through innovative technology.

## Scenario

As a junior data analyst on Bellabeat's marketing team, your task is to analyze fitness data from smart devices to uncover trends in consumer usage. Bellabeat, a growing tech company specializing in women's wellness products, aims to expand its global presence. Urška Sršen, co-founder and Chief Creative Officer, believes that studying this data can reveal opportunities for growth. Your analysis will focus on one of Bellabeat’s products, and the insights you generate will shape the company’s marketing strategy. You’ll present your findings and strategic recommendations to the executive team to help drive Bellabeat’s future success.

This project follows the six-step data analysis process outlined in the Google Data Analytics Certificate:

    Ask – Define the business problem.

    Prepare – Gather and organize relevant data.

    Process – Clean and validate the data.

    Analyze – Identify patterns and trends.

    Share – Present findings through visualizations and reports.

    Act – Recommend strategies based on insights.

## ⚙ Approach/Steps
### 1. Ask

Urška Sršen has tasked you with analyzing data on how consumers use non-Bellabeat smart devices to uncover behavioral trends. Based on these insights, you will then choose one Bellabeat product to focus on and demonstrate how these findings can inform its marketing strategy.

The analysis should address the following three key questions:


   1. What are some trends in smart device usage?
   2. How could these trends apply to Bellabeat customers?
   3. How could these trends help influence Bellabeat marketing strategy?

### 2. Prepare

I will use FitBit Fitness Tracker Data, a valuable historical dataset provided by Motivate International Inc. under license, to analyze trends in BellaBeat usage from 2016.
This Kaggle dataset includes fitness tracking data from 30 Fitbit users who agreed to share their personal activity metrics. The dataset provides granular minute-level details on physical movement, heart rate, and sleep patterns, along with daily summaries of steps and overall activity. These metrics offer valuable insights into user behavior and exercise trends.

**Data Source:** [Bella-Beat](https://www.kaggle.com/arashnic/fitbit)<br>
[Note that the data has been made available by Motivate International Inc. under this [<ins>license</ins>](https://creativecommons.org/publicdomain/zero/1.0/).

**Tools:** <br>
- Data cleaning & processing - SQL on PostgreSQL
- Data visualization - Microsoft Power BI

### 3. Process
The basis for this analysis is **2016** data and the steps for processing the data are as follow:

![Data Modeling](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/DataModelingBellaBeat.sql)

![Data Transformation](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/DataTransformationBellaBeat.sql)

![Data Combining](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/DataCombiningBellaBeat.sql)

![Data Exploration](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/DataExplorationBellaBeat.sql)

![Data Analysis](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/Data%20Analysis.sql)

#### Data Combining

After exporting 6 tables to PostgreSQL, the next step involved merged the tables hourly_calories, hourly_intensities, and hourly_steps to consolidate relevant metrics such as calories consumed, total intensity, average intensity, and step counts into a unified structure.

Since the tables have Id, date_new and time_new in common was used Inner Join to facilitate streamlined data analysis and reporting.

#### Data Exploration

Before cleaning the data, one of the first steps I took was to familiarize myself with the table's structure and its data to identify potential inconsistencies.

During the initial data assessment, it was noted that only the sleep_data table contained records for 24 distinct users, whereas all other tables consistently included data for 33 users each. This discrepancy in participant representation across datasets may introduce biases or limitations when analyzing relationships between sleep metrics and other activity variables (e.g., steps, calories). 

A review of all six tables confirmed the absence of null values and duplicate records, indicating high data completeness and cleanliness. 

### 4. Analyze

The analysis question is:

How could these trends help influence Bellabeat marketing strategy?

To streamline the analysis and maintain consistency, the data tables—which track various fitness metrics like steps, calories, distance, sleep, and activity—will be categorized based on their time intervals (daily or hourly). Since all tables share the "Id" column as a common identifier, this grouping allows for easier pattern recognition and conclusions. By organizing the data this way, the analysis becomes more structured and manageable.

![Pie Chart Time Spent in a day](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/pie%20chart.png)

Key Insights:

* Sedentary Time Dominates (73.29%)
* Light Activity is Modest (22.29%)
* Very Low Active Time (2.58% Very Active, 1.84% Fairly Active)

![Total Distance and Average Calories Burned by Day of week](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/Total%20Distance.png)

Key Insights:

* At 1773, Tuesday had the highest Total Distance and was 45.74% higher than Sunday, which had the lowest Total Distance at 1,216.58.
* Total Distance and total Total Calories are positively correlated with each other.
* Tuesday accounted for 17.18% of Total Distance.
* Total Calories and Total Distance diverged the most when the day_of_week was Tuesday, when Total Calories were 714455 higher than Total Distance.

![Average Distance and Average Calories Burned by Day of week](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/average%20distance.png)

key insights:

* At 5.85, Saturday had the highest Average Distance and was 16.46% higher than Sunday, which had the lowest Average Distance at 5.03.
* Average Distance and total Average Calories Burned are positively correlated with each other.
* Saturday accounted for 15.26% of Average Distance.
* Average Calories Burned and Average Distance diverged the most when the Day of Week was Tuesday, when Average Calories Burned were 2,350.18 higher than Average Distance.

![Table](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/Screenshot%202025-04-07%20at%2009.56.48.png)
![Scarter plot 3 together](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/3%20scarter%20plot.png)

Key insights:

* Low Active Minutes (R² = 0.0118): Minimal correlation with calorie expenditure.
* Fairly Active Minutes (R² = 0.0391): Slightly stronger but still weak correlation.
* Very Active Minutes (R² = 0.3865): Demonstrates a much stronger correlation, indicating that higher-intensity activities significantly impact calorie burn.

As activity intensity and duration increase, the R-squared values rise, showing a clear trend: more vigorous and prolonged exercise leads to greater calorie expenditure. This suggests that focusing on high-intensity workouts is far more effective for burning calories compared to low or moderate activity.

![column chart calories burned vc time of day](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/column%20chart.png)

Key insights:

* The data suggests a strong link between activity intensity and calories burned, with higher-intensity movement likely contributing significantly to energy expenditure.
* Additionally, the graph indicates that peak activity periods occur between 7:00 AM and 8:00 PM, aligning with typical waking hours when users are most engaged in physical 

![table charts](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/table.png)
![scarter chart](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/table%20and%20scarter%20chart.png)

Key Findings:

* The analysis reveals a strong positive correlation (R² = 0.8727) between sleep duration and calories burned, indicating that longer, high-quality sleep is linked to greater calorie expenditure.
* However, the relationship is not linear indefinitely—exceeding optimal sleep duration does not increase calorie burn and may instead reduce it. This suggests that while adequate sleep supports metabolism, excessive sleep could have diminishing returns or even negative effects on energy expenditure.

![table and scarter chart](https://github.com/Juliana-89/Bellabeat-Case-Study-SQL-and-Power-BI/blob/main/table%20and%20scarter%20plot.png)

Key insights:

* The R-squared value is 0.5504 
* Indicating a strong positive correlation between METs and average calories burned.

The number of calories burned by each user is significantly influenced by their daily MET values. This relationship is evidenced by a high r-squared value, indicating a strong correlation between the trend line and the dataset points.

### 5. Share

After processing the given datasets through collection, transformation, cleaning, organization, and analysis, we have sufficient factual evidence to address the initial business-related questions.

Our findings indicate that both the duration and intensity of physical activities significantly influence calorie expenditure. METs (Metabolic Equivalent of Task) offer valuable insights into activity intensity and calories burned per minute. While most consumers get adequate sleep, a small portion either oversleeps or undersleeps. Additionally, users tend to engage in low-to-high intensity activities primarily between 7:00 AM and 8:00 PM daily.

### 6. Act

Key Recommendations for Marketing Strategists:

1. Promote MET Tracking as a Key Feature – Leverage MET (Metabolic Equivalent of Task) tracking in marketing campaigns to educate users on how it measures activity intensity and provides real-time calorie burn insights. This can help users optimize their workouts and stay motivated.
2. Encourage Activity During Peak Hours – Since data shows users are most active between 7:00 AM and 8:00 PM, smart devices can send timely reminders during these windows to prompt movement, helping combat sedentary behavior and promoting a more active lifestyle.
3. Enhance Sleep Tracking & Notifications – Implement smart notifications to encourage consistent, quality sleep. Introduce advanced sleep metrics like REM (Rapid Eye Movement) tracking to provide deeper insights and improve user sleep habits.
4. Introduce Gamified Calorie Challenges – Boost engagement by setting daily/weekly calorie-burning challenges with a rewards system. Top performers could earn redeemable points for discounts on future purchases, fostering loyalty and motivation.

By incorporating these strategies, the business can drive user engagement, improve health outcomes, and unlock new growth opportunities.

## 🔮 Conclusion
This analysis offers key insights into the distinct behaviors and preferences of BellaBeat users. By adapting strategies to these differences, the company can more effectively encourage casual users to become potential members.


        









