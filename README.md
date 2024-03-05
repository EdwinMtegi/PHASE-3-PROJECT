**INTRODUCTION**

In today's highly competitive telecommunications industry, customer churn poses a significant challenge for companies striving to maintain market share and profitability. SyriaTel, a leading telecommunications provider in Syria, is no exception. With increasing competition and evolving customer expectations, understanding the factors influencing churn and implementing effective retention strategies are essential to sustaining business success. This project aims to analyze SyriaTel's customer data, identify key drivers of churn, and develop actionable insights to reduce churn rates and enhance customer retention. 

**OBJECTIVES**

The objectives of this project are:

1. Data Exploration and Preprocessing: Explore and preprocess SyriaTel's customer data to ensure data quality and suitability for analysis.
2. Feature Selection and Engineering: Identify relevant features and engineer new features that may contribute to predicting customer churn.
3. Model Development and Evaluation: Develop predictive models using machine learning algorithms to accurately predict customer churn. Evaluate model performance using appropriate metrics.
4. Insights Generation: Interpret model results to identify key drivers of churn and gain actionable insights into customer behavior and preferences.
5. Recommendation Formulation: Formulate actionable recommendations based on insights generated to mitigate churn and improve customer retention.

**BUSINESS UNDERSTANDING**

**Stakeholder and Business Problem**

SyriaTel is facing a growing challenge of customer churn, which not only impacts its revenue and profitability but also undermines its market competitiveness and brand reputation. The company aims to understand the underlying reasons driving churn among its subscriber base and implement effective strategies to mitigate churn rates. By leveraging advanced analytics and predictive modeling techniques, SyriaTel seeks to proactively address customer churn and foster long-term relationships with its subscribers. The audience of this project findings would be the telecommunication company, Syriatel. The findings and recommendations will help reduce the amount of customer churn, thus reducing the amount of losses incurred as a result. 

**DATA UNDERSTANDING**

This data was extracted from Kaggle with the following description of the features.

1. State: The state in which the customer resides.
2. Account Length: The number of days the customer has been with the company.
3. Area Code: The area code associated with the customer's phone number.
4. Phone Number: The customer's phone number, which serves as a unique identifier.
5. International Plan: Whether the customer has an international calling plan (Yes/No).
6. Voice Mail Plan: Whether the customer has a voicemail plan (Yes/No).
7. Number Vmail Messages: The number of voicemail messages the customer has.
8. Total Day Minutes: The total number of minutes the customer used during the daytime.
9. Total Day Calls: The total number of calls the customer made during the daytime.
10. Total Day Charge: The total charge for daytime usage.
11. Total Eve Minutes: The total number of minutes the customer used during the evening.
12. Total Eve Calls: The total number of calls the customer made during the evening.
13. Total Eve Charge: The total charge for evening usage.
14. Total Night Minutes: The total number of minutes the customer used during the night.
15. Total Night Calls: The total number of calls the customer made during the night.
16. Total Night Charge: The total charge for nighttime usage.
17. Total Intl Minutes: The total number of international minutes used by the customer.
18. Total Intl Calls: The total number of international calls made by the customer.
19. Total Intl Charge: The total charge for international calls.
20. Customer Service Calls: The number of customer service calls made by the customer.
21. Churn: The target variable indicates whether the customer churned (i.e., stopped doing business with the company).

**DATA PREPARATION**

Several steps were taken to ensure the reliability of the data for training and developing a churn prediction model. These processes involved several critical steps aimed at enhancing data quality and feature representation. Initially, we addressed missing values and detection techniques, to prevent them from skewing our model's performance. Additionally, feature engineering was conducted to derive new variables that could potentially capture underlying patterns related to churn behavior more effectively. This involved creating new features, such as average eve call charge, to provide a more comprehensive view of company charges. Furthermore, we transformed categorical variables into a numerical format using techniques like one-hot encoding to enable their incorporation into machine learning algorithms. Irrelevant columns that were not contributing to the project goal were also dropped. 

**EXPLORATORY DATA ANALYSIS**
![CURVES](https://github.com/EdwinMtegi/PHASE-3-PROJECT/assets/151729172/82301ffe-6ec6-46c3-af18-b3bd244954e4)

Most of the features exhibit a bell-shaped curve, indicating an even distribution around the mean. However, the number of vmail messages feature displays a different pattern, which suggests a division in the data, possibly indicating distinct user behaviors or preferences regarding voicemail usage. The customer service calls feature also demonstrates an irregular curve fluctuating throughout the plot. This irregular pattern suggests variability or inconsistency in the frequency of customer service calls across the data. 
