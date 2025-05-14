<h1 align="center">Full-Stack Data Analytics Project: From ETL and SQL to Power BI Dashboards and Predictive Modeling with Python</h1>


#  Introduction
In the contemporary business landscape, customer retention is a critical determinant of sustainable growth and profitability. Churn analysis has emerged as a strategic approach for identifying and mitigating customer attrition. This analytical technique entails the systematic examination of customer behavior and transactional data to uncover patterns and root causes of customer disengagement. By leveraging advanced data analytics and machine learning methodologies, organizations can accurately forecast which clients are at a heightened risk of churn and gain actionable insights into the underlying drivers of their decisions. Equipped with this intelligence, companies are better positioned to implement targeted interventions aimed at enhancing customer satisfaction, fostering brand loyalty, and ultimately securing a competitive advantage.

![Churn Summary](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Images/Churn%20Prediction.png)


##  Table of Contents

1. [Introduction](#introduction)  
2. [Data](#data)  
3. [Resources and Tools Used](#resources-and-tools-used)  
4. [Target Audience](#target-audience)  
5. [Key Performance Indicators (KPIs)](#key-performance-indicators-kpis)  
6. [Methodology](#methodology)  
7. [Data Transformation Using Power Query](#data-transformation-using-power-query)  
8. [Machine Learning Model for Churn Prediction](#machine-learning-model-for-churn-prediction)  
9. [Conclusion](#conclusion)  

#  **Data**

Download the dataset used for this project [here](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Data/Customer_Data.csv)
## **Disclaimer**
*This dataset is entirely fictitious and has been created solely for the purpose of this portfolio project. The data does not represent real customer information and should not be interpreted as actual business insights or factual analysis.*

*Any resemblance to real individuals, businesses, or transactions is purely coincidental. The dataset has been structured to simulate a realistic business scenario for analytical and machine learning purposes. As such, findings, trends, and predictions derived from this data should be regarded as illustrative examples rather than actionable business conclusions.*

*This report and its accompanying data are intended for **educational and demonstration purposes only**.*

### Project Objective

The primary objective of this project is to design and implement a comprehensive Extract, Transform, Load (ETL) pipeline within a relational database environment, coupled with the development of an interactive Power BI dashboard. The solution aims to effectively leverage customer data to achieve the following strategic goals:

- Deliver multi-dimensional analysis and visualisation of customer data across key domains:
  - **Demographic** attributes  
  - **Geographic** distribution  
  - **Payment and Account Information**  
  - **Service Subscription Details**

- Examine the profiles and behavioral patterns of customers who have churned, with the intent of identifying actionable insights for targeted marketing interventions.

- Develop a predictive framework capable of identifying customers with a high likelihood of future churn, enabling proactive customer retention strategies.

---

## **Tools & Technologies Used in the Project**

- **Excel** – Used for initial data cleaning, preprocessing, and structuring.
- **SQL** – Employed for data extraction, transformation, and preparation using advanced querying techniques (e.g., CTEs, joins, window functions). [Click here for the SQL syntaxes and technical details used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/SQL%20Queries%20Churn%20Analysis.pdf)
- **Power BI** – Developed dashboards and reports for dynamic visualization and stakeholder insights. [Click here for the DAX formulas used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/Power%20Query%20Transformations%20%26%20Measures.pdf)

- **Python (Jupyter Notebook)** – Implemented churn prediction models using libraries such as `pandas`, `scikit-learn`, and `matplotlib`. [Click here for the Python codes used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/Python%20Codes%20for%20Random%20Forest%20Churn%20Analysis.pdf)

- **VS Code** – Used for scripting and development across SQL Python, and Power BI (including Power Query and DAX).

---

### Target Audience

While this project is anchored in the context of a telecommunications firm, the methodologies, analytical frameworks, and insights derived are broadly applicable across multiple industry verticals. Sectors such as retail, financial services, and healthcare—where customer retention is a strategic imperative—stand to benefit significantly from the adoption of churn analysis techniques. 

This report is intended for business analysts, data professionals, customer experience strategists, and decision-makers seeking to leverage data-driven approaches to mitigate customer attrition. By exploring proven tools, methodologies, and best practices, this study aims to equip stakeholders with the knowledge required to translate complex data into actionable strategies that foster customer loyalty and drive long-term business sustainability.
---

### Key Performance Indicators (KPIs)

To monitor performance and derive actionable insights, the following core metrics will be tracked and visualised:

- **Total Customers**  
- **Total Churn**  
- **Churn Rate**  
- **New Customer Acquisition (New Joiners)**
---

#  Methodology


Key Activities
1. Data Exploration and Profiling
Structured Query Language (SQL) was employed to conduct a detailed analysis of categorical variables, including Gender, Contract Type, State, and Customer Status. Distribution and proportion metrics were calculated to derive insights into customer demographics and behavioral patterns. This preliminary profiling facilitated a foundational understanding of key characteristics influencing churn.[Click here for the SQL syntaxes and technical details used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/SQL%20Queries%20Churn%20Analysis.pdf)

2. Missing Data Handling
A comprehensive null-value audit was executed across all dataset fields to identify gaps in data completeness. Missing entries were addressed using contextually appropriate default values (e.g., ‘No’, ‘None’, ‘Others’) to enhance data integrity and prepare the dataset for downstream analytical processes.

3. Data Transformation and Loading
A refined production table (prod_Churn) was engineered from the raw staging table (stg_Churn). The transformation process involved the application of ISNULL() functions for imputing missing values and the implementation of standardized mappings to harmonize categorical attributes. This ensured a consistent and analysis-ready data structure.[Click here for the SQL syntaxes and technical details used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/SQL%20Queries%20Churn%20Analysis.pdf)

4. View Creation for Business Intelligence Integration
To support efficient data visualization and reporting, two SQL views (vw_ChurnData and vw_JoinData) were developed. These views segment customer records based on their status—Churned, Stayed, or Joined—thereby facilitating seamless integration with Power BI. This enabled real-time data accessibility for stakeholders and enhanced the clarity of business performance dashboards.
[Click here for the DAX formulas used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/Power%20Query%20Transformations%20%26%20Measures.pdf)


## **Data Transformation Using Power Query**
To ensure data consistency and enhance usability, several preprocessing steps were undertaken in Power Query:

### **1. Churn Status Identification**
- A new column, `Churn Status`, was created to classify customers as churned (`1`) or active (`0`).

### **2. Monthly Charge Categorization**
- Customers were grouped into predefined pricing tiers based on monthly charges.

### **3. Age Group Mapping**
- A reference table was established, sorting customers into age categories for better demographic insights.

### **4. Tenure Group Mapping**
- Customers were categorized based on their subscription duration to understand loyalty and engagement trends.

### **5. Service Data Unpivoting**
- The existing service-related columns were unpivoted to structure customer service engagement data more effectively.

## **Summary Page Measures**

![Churn Summary](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Images/Churn%20Sumary.png)


Several key metrics were calculated to summarize customer behavior and churn rate:

- **Total Customers**: Represents the count of unique customer IDs.
- **New Joiners**: Filters customers who recently subscribed.
- **Total Churn**: Computes the number of churned customers.
- **Churn Rate**: Determines the proportion of churned customers relative to total subscribers.
- 
[Click here for the DAX formulas used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/Power%20Query%20Transformations%20%26%20Measures.pdf)

## **Machine Learning Model for Churn Prediction**
To enhance predictive capabilities, a **Random Forest Classifier** was employed using Python within Jupyter Notebook.   [Click here for the Python codes used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/Python%20Codes%20for%20Random%20Forest%20Churn%20Analysis.pdf)
### **1. Data Preprocessing**
- Irrelevant columns were dropped.
- Categorical variables were transformed via label encoding.
- The dataset was split into training and test sets for model development.
![](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Images/Churn%20Prediction.jpg)

### **2. Model Training & Evaluation**
- A **Random Forest Classifier** was trained on the dataset.
- Performance was assessed using a **confusion matrix** and **classification report**.
- Feature importance analysis was conducted to determine the most influential factors driving churn.  [Click here for the Python codes used](https://github.com/evansory/CHURN-ANALYSIS/blob/main/Codes%2C%20Queries%20%26%20DAX/Python%20Codes%20for%20Random%20Forest%20Churn%20Analysis.pdf)
### **3. Predictive Analysis on New Customer Data**
- The trained model was used to forecast customer churn likelihood.
- Predictions were integrated into a separate dataset for reporting.
- The resulting predictions were saved for further business insights and strategic planning.



## **Conclusion**
This project successfully implemented **data transformations, statistical measures, and predictive modeling** to analyze customer churn patterns. By leveraging **Power Query transformations and machine learning algorithms**, the business can proactively identify customers at risk of churning and develop effective retention strategies.

Future enhancements may incorporate **additional customer attributes, deep learning models, and real-time predictive analytics** to further refine churn prediction accuracy.
