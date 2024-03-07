**TABLE OF CONTENTS**

- INTRODUCTION
- OBJECTIVES
- BUSINESS UNDERSTANDING
- DATA UNDERSTANDING
- DATA PREPARATION
- EXPLORATORY DATA ANALYSIS
- EVALUATION
- CONCLUSION
- RECOMMENDATION


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

Most of the numeric features exhibit a bell-shaped curve, indicating an even distribution around the mean. However, the number of vmail messages feature displays a different pattern, which suggests a division in the data, possibly indicating distinct user behaviors or preferences regarding voicemail usage. The customer service calls feature also demonstrates an irregular curve fluctuating throughout the plot. This irregular pattern suggests variability or inconsistency in the frequency of customer service calls across the data. 

![categorical](https://github.com/EdwinMtegi/PHASE-3-PROJECT/assets/151729172/aada3cbb-6eb5-4d65-8727-206641527792)
The categorical features shows that most customers do not have international plan or voice mail plan. 

![CHURN VS CAT](https://github.com/EdwinMtegi/PHASE-3-PROJECT/assets/151729172/cd4d3e11-d859-4490-a8c9-e0ad99de5bd5)
There are distinct patterns across the numerical features. Each feature is depicted by a box plot, with a central line representing the median value.While most features exhibit a balanced distribution around this midpoint, deviations are evident. Some features display a clustering of values towards higher or lower extremes, indicating instances of higher-than-average or lower-than-average values. While its clear that there are outliers, it's essential to recognize their significance, especially in the context of customer churn analysis since each outlier represents a unique case that deviates significantly from the majority of the data points. 

![churn vs var](https://github.com/EdwinMtegi/PHASE-3-PROJECT/assets/151729172/8e75dc73-5174-4a2c-93ee-bff6f88abddc)

For the categorical variables, the plots show that customers without international are less likely to churn and also customers without voice mail plan are less likely to churn.

**EVALUATION**
![models](https://github.com/EdwinMtegi/PHASE-3-PROJECT/assets/151729172/76f3d0d8-71c8-490f-af7e-3f9e86829ffb)
Logistic regression model yields an accuracy of 87%, adaboost -88%, gradient boost -92%, XGBoost - 92%, random forests - 92%. However, XGBoost and gradient boost has a low precision in predicting churn cases, that is 64% and 76% respectively. Random forests demonstrate a strong overall performance in predicting customer churn. With an accuracy of 92.46%, the model is able to correctly classify the majority of instances. The precision for predicting non-churners (class 0) is high at 94%, indicating a low false positive rate, while the precision for predicting churners (class 1) is 78%, suggesting a moderate false positive rate. The recall, or true positive rate, is 61% for class 1, indicating that the model captures a significant portion of the actual churn cases. The F1-score, is 68% for class 1, reflecting a reasonable trade-off between precision and recall. The confusion matrix shows that the model correctly identifies 559 non-churners and 54 churners, while misclassifying 15 non-churners as churners and 35 churners as non-churners. Overall, considering the high accuracy and reasonable precision and recall values, the Random Forest model appears to be a suitable choice for predicting customer churn in this scenario. 

**FEATURE IMPORTANCE ON SELECTED RANDOM FOREST MODEL**
![FEAT](https://github.com/EdwinMtegi/PHASE-3-PROJECT/assets/151729172/740edf34-2d4b-474d-af4e-af496fd7be20)
Higher total day charges and longer day call durations suggest dissatisfaction with daytime calling plans or high costs, potentially driving customers to switch providers. An increased number of customer service calls indicates unresolved issues or dissatisfaction, highlighting the importance of prompt and effective problem resolution to enhance customer satisfaction. Customers with international plans and longer international call durations are more likely to churn, indicating dissatisfaction with international calling services or costs. Additionally, high evening and night call charges may signal dissatisfaction with service quality, prompting telecom companies to reassess their evening calling packages. 

**CONCLUSION**

In conclusion, this project aimed to analyze customer churn in the telecommunication industry and identify key factors influencing churn behavior. Through the exploration of various machine learning models that is; logistic regression, random forest, AdaBoost, and gradient boosting, we discovered that factors such as total day charges, total day minutes, customer service calls, international plan usage, and average international call duration significantly impact churn rates. Leveraging these insights, SyriaTel can implement targeted strategies to improve customer retention, such as enhancing customer service responsiveness, optimizing calling plans, and tailoring promotions based on usage patterns. By prioritizing customer satisfaction and addressing underlying reasons for churn, syriaTel can foster stronger customer relationships and sustain business growth. Additionally, ongoing analysis and adaptation of strategies based on evolving customer preferences are crucial for maintaining competitiveness in the dynamic telecommunications market.

**RECOMMENDATIONS**

1. Enhancing Customer Support: Given the observed impact of customer service calls on churn rates, SyriaTel should prioritize enhancing the quality and responsiveness of its customer support services. This could involve investing in comprehensive training programs for customer service representatives, implementing efficient call handling processes, and promptly addressing customer queries and concerns.

2. Revising Calling Plans: SyriaTel should review its calling plans, particularly focusing on factors like total day charges, total day minutes, and international plan usage, to ensure they align with customer expectations and market competitiveness. Offering flexible and value-driven calling plans that cater to diverse customer needs can help retain existing subscribers and attract new ones.

3. Personalizing Offers and Promotions: Utilizing customer data analytics, SyriaTel can develop personalized offers and promotions tailored to individual preferences and usage patterns. By understanding customer behavior, such as average international call duration and evening call usage, the company can offer targeted incentives to encourage loyalty and increase customer satisfaction.

3. Proactive Monitoring and Analysis: Implementing robust data monitoring and analysis practices will enable SyriaTel to detect early signs of customer churn and take proactive measures to mitigate it. Leveraging advanced analytics tools and machine learning algorithms can provide deeper insights into customer behavior, allowing for timely intervention and targeted retention strategies.

4. Improved Communication Channels: SyriaTel should establish effective communication channels to keep customers informed about relevant offers, updates, and service improvements. Leveraging multiple channels such as SMS notifications, email campaigns, and personalized messages will enhance customer engagement and satisfaction.

6. Focus on Customer Experience: Enhancing the overall customer experience should be a priority for SyriaTel. This involves investing in user-friendly interfaces, self-service options, and seamless customer journeys across all touchpoints. By prioritizing customer-centricity, SyriaTel can foster stronger relationships with its subscribers and foster long-term loyalty.

Implementing these recommendations will enable SyriaTel to effectively reduce churn rates, improve customer retention, and position itself as a leading telecommunications provider in the Syrian market








