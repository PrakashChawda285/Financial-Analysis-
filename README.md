# Financial-Analysis-
I recently completed a data analytics project focused on analyzing credit card customer data to evaluate financial performance and identify high-risk customers. Using Power BI, I developed interactive dashboards and calculated key KPIs such as utilization ratio, delinquency rate, customer churn, and transaction growth.





Credit Card Financial Performance & Risk Analytics
[A] Project Overview

This project focuses on analyzing credit card customer data to evaluate financial performance, customer behavior, and credit risk exposure. Using Power BI, key financial indicators such as utilization ratio, delinquency rate, transaction growth, and customer churn were measured to support data-driven decision-making in the banking industry.

The project demonstrates how analytics can help financial institutions reduce risk, improve profitability, and better understand customer behavior.

[B] Business Problem

Banks manage millions of credit card customers but face challenges in balancing profitability with risk management.

Key challenges:

Identifying high-risk customers
Understanding customer spending behavior
Measuring customer retention and churn
Monitoring credit utilization
Maintaining financial profitability

Without proper analytics, banks may:

Approve loans for risky customers
Lose profitable customers
Fail to detect credit risk early

[C] Project Objectives
Analyze customer financial behavior
Calculate key financial KPIs
Identify high-risk customers
Measure transaction trends
Evaluate relationship between income and credit limit
Support strategic decision-making with insights

[D] Dataset Description
Customer Table
Column	Description
Client_Num	Unique customer ID
Income	Customer income
Customer_Age	Age of customer
Education	Education level
Marital_Status	Marital status
Card_Category	Card type
Personal_Loan	Loan status
Credit Card Transaction Table
Column	Description
Total_Trans_Amt	Total transaction amount
Total_Trans_Ct	Total transaction count
Credit_Limit	Credit limit
Avg_Utilization_Ratio	Credit utilization
Total_Revolving_Bal	Outstanding balance
Delinquent_Acc	Delinquent accounts
Interest_Earned	Interest earned
Cust_Satisfaction_Score	Customer satisfaction score
🛠 Tools & Technologies
Power BI Desktop → Data visualization & dashboards
Power Query → Data cleaning & transformation
DAX (Data Analysis Expressions) → KPI calculations
Data Modeling → Relationship building between tables
Risk Scoring Model → Identify high-risk customers

[E] Key Performance Indicators (KPIs)
Financial Metrics
Total Transaction Amount
Interest Earned %
Average Credit Limit
CAC Ratio
Month-over-Month Growth
Week-over-Week Growth
Risk Metrics
Credit Utilization Ratio
Delinquency Rate
Credit Risk Score
High Risk Customers
Customer Metrics
Customer Churn
Satisfaction Score
Income vs Credit Limit Correlation

[F] Key DAX Measures
Running Total Transactions
RUNNING_TOTAL_CREDIT_CARD =
CALCULATE(
    SUM(Credit_card[Total_Trans_Amt]),
    Calendar[Date] <= MAX(Calendar[Date])
)
Credit Risk Flag
High_risk_flag =
IF(
Credit_card[Total_revolving_bal] > 0.9 * Credit_card[Credit_limit]
&& Credit_card[Avg_Utilization_Ratio] > 0.8,
"High Risk",
"Normal"
)
Delinquency Rate
DELINQUENCY_RATE =
DIVIDE(
COUNTROWS(
FILTER(Credit_card, Credit_card[Delinquent_Acc] > 0)
),
COUNTROWS(Credit_card)
)
Month-over-Month Growth
MOM_GROWTH =
VAR PrevMonth =
CALCULATE(
SUM(Credit_card[Total_trans_amt]),
DATEADD(Calendar[Date],-1,MONTH)
)
VAR CurrentMonth =
SUM(Credit_card[Total_trans_amt])

RETURN
DIVIDE(CurrentMonth - PrevMonth, PrevMonth)

[G] Key Insights
46M total transaction amount processed
6.06% delinquency rate observed
112 high-risk customers identified
66.63% interest earned ratio
10.27% month-over-month growth
0.27 average utilization ratio

[H] Data Analysis Process
1️⃣ Data Cleaning
Removed null values
Corrected data types
Handled missing credit limits
Removed duplicate records
2️⃣ Data Modeling
Built relationships using Client_Num
Created star schema model
3️⃣ Data Analysis
Created DAX measures
Calculated financial ratios
Developed risk scoring model

[I] Project Outcomes
Identified high-risk customers
Analyzed customer behavior patterns
Generated financial KPIs
Created interactive dashboard
Provided decision-support insights

[J] Limitations
Dataset contains limited variables
External economic factors not included
Model assumes historical patterns continue
Behavior changes may affect accuracy

[K] Future Improvements
Machine Learning risk prediction model
Customer segmentation using clustering
Transaction forecasting
Fraud detection system
Real-time data integration

[L] Recommendations
Reduce credit limits for high-risk customers
Create retention strategies to reduce churn
Monitor high utilization customers
Improve satisfaction for premium customers
Adjust credit policies based on income correlation


Link : https://drive.google.com/drive/folders/1EnCLZeTZ2EwLG2owmfgcXdG4mvNyzo5u
