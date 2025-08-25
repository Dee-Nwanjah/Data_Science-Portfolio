# Data_Science-Portfolio
This Repo contains projects that demonstrate my end-to-end data science knowledge and skills


Auto Data Quality Report Analysis
This project provides a basic set of tools for analyzing data quality issues within a dataset. I included functions for detecting missing data, outliers, duplicates, and consistency problems, and generated both a detailed text report and a visual dashboard.

The Features Include:
Missing Data Analysis: Identifies columns with missing values and reports their count and percentage.
Outlier Detection: Detects outliers in numeric columns.
Duplicate Check: Checks for duplicate records.
Data Consistency Analysis: Identifies inconsistencies in text data.
Automated Reporting: Generates a detailed text report summarizing data quality findings.
Visual Dashboard: Creates a visual dashboard for a quick overview of data quality.
Report Saving: Saves the text report and detailed data quality findings to files.
Quality Score: Calculates an overall data quality score.
Usage
Load the data into a pandas DataFrame.
Use the provided functions to analyze data quality issues (analyze_missing_data, detect_outliers, check_duplicates, analyze_data_consistency).
Generate a data quality report (generate_data_quality_report).
Create a visual dashboard (create_quality_dashboard).
Save the reports (save_quality_report).
Core Components
analyze_missing_data(df): Analyzes missing values.
detect_outliers(df, numeric_columns): Detects outliers.
check_duplicates(df): Checks for duplicates.
analyze_data_consistency(df): Analyzes data consistency.
generate_data_quality_report(df, dataset_name): Generates a text report.
create_quality_dashboard(df, report_data): Creates a visual dashboard.
save_quality_report(report_text, report_data, filename_prefix): Saves reports.
Sample Data
A sample dataset (sample_sales_data.csv) was created and used in the notebook to demonstrate the tool's functionality.

Reports and Dashboard
The tool generates a text report summarizing the findings and a visual dashboard to visualize the data quality issues. Examples of these outputs are included in the notebook.



COVID-19 Data Explorer
Project Description
This is a project I created to explore and visualize global COVID-19 data using Python, specifically leveraging the power of pandas for data manipulation, plotly for interactive visualizations, and streamlit to build an interactive web application. I downloaded the latest COVID-19 data from Our World in Data and performed cleaning, preparation, and various analytical tasks to understand trends, country comparisons, vaccination progress, and correlations with demographic factors.

Setup and Installation
To run this project, you will need a Python environment with the necessary libraries installed. The easiest way to get started is by using Google Colaboratory (Colab), which provides a free, cloud-based Jupyter notebook environment.

Open the Colab Notebook: Access the Colab notebook associated with this project.
Install Dependencies: I used the following libraries, which you can install using pip:

    import subprocess
    import time
    from google.colab import userdata
    import os
    from pyngrok import ngrok

    # ... (code to get authtoken and start streamlit) ...

    # Use pyngrok to connect
    try:
        # ... (pyngrok connection code) ...
        public_url = ngrok.connect(8501).public_url
        print(f"Your Streamlit app is available at: {public_url}")
        # ... (rest of the code) ...
    except Exception as e:
        # ... (error handling) ...
        pass # or other error handling

    # ... (code to keep cell running) ...
     
Your Streamlit app is available at: https://fbfc47e3af13.ngrok-free.app

STEPS TO FOLLOW:
Open the Colab Notebook: Access the Colab notebook associated with this project.
Install Dependencies: In the Colab notebook, I used pip to install the required libraries:
!pip install streamlit pandas numpy plotly requests pyngrok
Set up ngrok: I used ngrok via the pyngrok library to create a public URL for the Streamlit app running in the Colab environment. You will need an ngrok authtoken for this. You can get one for free from the ngrok dashboard: https://dashboard.ngrok.com/get-started/your-authtoken. Once you have your authtoken, add it to Colab's Secrets manager (the "🔑" icon in the left sidebar) with the name NGROK_AUTH_TOKEN.

Run the Streamlit App: In the Colab notebook, I included a cell that runs the app.py script and uses pyngrok to create a public tunnel to the Streamlit app. Execute that cell. You should see output indicating that the ngrok tunnel has been established and providing a public URL.

HOW TO Access the Web Application
Once the Streamlit app is running in the Colab notebook (after executing the cell mentioned in step 4 above), you can access the interactive dashboard using the public URL provided in the output of that cell.

Streamlit App Public URL (via ngrok): [YOUR_NGROK_URL_HERE]

You should note that This URL is temporary and will only be active while the Colab notebook is running and the cell with the ngrok setup is executing. Remember to replace [YOUR_NGROK_URL_HERE] with the actual URL you get from the Colab output.

Project Structure
app.py: Contains the Python code for the Streamlit web application, including data loading, cleaning, analysis functions, and the Streamlit layout.
This Colab Notebook: Provides the environment and steps I used to install dependencies, create the app.py file, and run the Streamlit application with ngrok.
Acknowledgments
Data is from Our World in Data.
Built with Streamlit and Plotly.



E-commerce Customer Analysis and Predictive Modeling
Project Overview
This project I performed a comprehensive analysis of an e-commerce customer dataset i downloaded from kaggle to understand customer behavior, segment the customer base, build predictive models for churn and future purchase behavior, and provide actionable recommendations to the business.

Data
The analysis uses the ecommerce_customer_data_large.csv dataset which is the dataset i got from kaggle.

All the initial steps i took:

I Loaded the dataset into a pandas DataFrame.
Checked the dataset shape and column names.
Displayed the head of the DataFrame to preview the data.
Examined data types.
Checked the date range of the purchase data.
Identified the number of unique customers and product categories.
There were also some additional data wrangling included which are: converting the 'Purchase Date' column to datetime objects and extracting 'Year', 'Month', 'Day', and 'Weekday' for time-based analysis.

Exploratory Data Analysis (EDA)
I calculated a couple of Key performance indicators (KPIs) in other to get an overview of the business performance which are as follows:

Total Revenue
Total Transactions
Total Customers
Average Order Value
Total Products Sold
Average Daily Customers
I also created a comprehensive dashboard to visualize key aspects of the e-commerce sales data. The dashboard includes plots for includes:

Monthly Revenue Trend
Top Products by Revenue
Sales by Day of Week
Transactions by Payment Method
Order Value Distribution
Monthly Active Customers
Customer Distribution by Age Group
Customer Distribution by Gender
These visualizations provide insights into sales patterns, popular categories and payment methods, and customer demographics.

Customer Segmentation
Customer segmentation was carried out using two approaches:

Simple Segmentation: I segmented customers based on their total spent and order count into 'VIP', 'High Value', 'Frequent', and 'Regular' categories.
RFM Analysis: Recency, Frequency, and Monetary values were calculated for each customer. I then segmented Customers based on quantiles of these RFM metrics, resulting in RFM scores (e.g., 444 for high Recency, Frequency, and Monetary).
Analysis of the RFM segments were included:

Examinined the distribution of customers across different RFM scores.
Calculated the average Recency, Frequency, and Monetary values for key segments to understand their characteristics (e.g., identifying high-value segments like 444 and low-value/inactive segments like 111).
Predictive Modeling
I built these Predictive models for two purposes:

Customer Churn Prediction
Data Preparation: I identified the target variable 'Churn'. I also selected some Relevant features and aggregated at the customer level, including demographic information, return behavior, and RFM metrics. Although Categorical features were so the models can easily understand.
Feature Engineering: I engineered New features to potentially improve the model performance, including Average Order Value, Return Frequency, and interaction terms between RFM metrics and customer age.
Model Selection: Random Forest Classifier and LightGBM Classifier were chosen as the initial models for binary classification.
Model Training: The data was split into training and testing sets (80/20 split), and both models were trained on the training data.
Model Evaluation: I evaluated the Model performance using metrics appropriate for imbalanced classification: Accuracy, Precision, Recall, F1-Score, and ROC-AUC score.
Results for Churn Prediction: Both the Random Forest and the LightGBM models showed high accuracy but very low Precision, Recall, and F1-Score, and ROC-AUC scores close to 0.5. This indicates that while the models can predict the majority class (non-churn) well, they are not really effective at identifying the minority churn class, likely due to the imbalanced nature of the dataset.

Future Purchase Prediction
Data Preparation: The target variable was defined as the 'Total Purchase Amount' in the next quarter following the last purchase date in the dataset. These Features were prepared based on historical data before the prediction period, including historical purchase metrics and customer characteristics. Categorical features were one-hot encoded as well.
Feature Engineering: Features such as Average Order Value and Most Frequent Product Category were engineered from historical data.
Model Selection: Random Forest Regressor and LightGBM Regressor were chosen as initial models for regression.
Model Training: The data was aslo split into training and testing sets (80/20 split), and both models were trained on the training data.
Model Evaluation: Model performance was evaluated using regression metrics: Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared (R2) score.
Results for Future Purchase Prediction: Both the Random Forest and the LightGBM models showed perfect MAE, RMSE, and R2 scores (0, 0, and 1.0 respectively). This highly unusual result was traced back to the target variable ('FutureTotalPurchaseAmount') containing only zero values in the defined prediction period. This indicates a critical data issue or misaligned prediction period, rendering these initial models for future purchase prediction ineffective.

Actionable Recommendations
Based on the insights gained from EDA, customer segmentation, and the predictive modeling attempts, the following actionable recommendations were provided, prioritized by potential impact and feasibility with Gemini's assistance:

High Priority Recommendations
Address the Future Purchase Prediction Target Variable Issue:

Problem/Opportunity: The target variable for future purchase prediction was zero for all customers, rendering the prediction models useless.
Action(s):
Verify the data source and extraction logic for the prediction period.
If data capture is incomplete or the period is not representative, redefine the prediction target (e.g., probability of any purchase in a longer timeframe, or total purchase amount over a different, valid period).
If predicting zero is the correct outcome for this specific period due to external factors, acknowledge this and shift focus to other predictive tasks or historical analysis.
Rationale: This is a critical data integrity issue. Resolving it is foundational for accurate future revenue forecasting and customer lifetime value analysis.
Focus on Customer Retention for At-Risk Segments:

Problem/Opportunity: Churn prediction models were ineffective, but RFM analysis identified segments with low Recency and Frequency (e.g., RFM 111, 211) who are likely inactive or low-engagement and at risk of churning.
Action(s):
Implement targeted re-engagement campaigns for customers in RFM segments with low Recency (Recency score 1 or 2). Use personalized emails with discounts, 'We miss you' messages, and tailored product recommendations.
Develop strategies to encourage repeat purchases for customers in RFM segments with low Frequency (Frequency score 1 or 2). Offer loyalty points for repeat buys, explore subscription options, or provide bundled offers.
Conduct targeted surveys or direct outreach to customers in low-engagement segments to understand their reasons for inactivity and gather feedback.
Rationale: Retaining existing customers is significantly more cost-effective than acquiring new ones. Proactive engagement with at-risk segments can directly prevent revenue loss.
Maximize Value from High-Value (VIP) Customers:

Problem/Opportunity: RFM analysis identified high-value segments (e.g., RFM 444, 344) who contribute the most to the business's revenue.
Action(s):
Implement a tiered loyalty program offering escalating benefits (e.g., increasing discounts, free/faster shipping, early access to sales/new products) for customers in higher RFM segments.
Provide personalized communication and potentially a dedicated customer support channel for top-tier VIP customers.
Organize exclusive events or offer premium products/services tailored to this group to enhance loyalty and encourage continued high spending.
Rationale: Nurturing high-value customers strengthens their loyalty, increases their lifetime value, and can lead to positive referrals, significantly impacting overall revenue.
Medium Priority Recommendations
Optimize Marketing and Product Strategies:

Problem/Opportunity: EDA revealed balanced popularity across key product categories. Customer segmentation provides insights into distinct customer preferences and behaviors.
Action(s):
Tailor marketing content (emails, ads, website banners) and personalized product recommendations based on customer segments and their most frequently purchased product categories.
Analyze purchasing patterns within different RFM segments to identify which product categories are most popular with high-value vs. low-value customers and adjust inventory, promotions, and merchandising accordingly.
Continue to ensure smooth operations and consistent effort across all payment methods and days of the week, as current analysis shows no major bottlenecks or significant variations in sales patterns.
Rationale: Aligning marketing and product efforts with customer segments and observed preferences improves campaign effectiveness and potentially increases sales efficiency.
Increase Average Order Value (AOV):

Problem/Opportunity: The order value distribution is heavily skewed towards lower amounts, indicating potential to increase the value per transaction.
Action(s):
Implement a free shipping threshold set slightly above the current average order value to encourage customers to add more items to their cart.
Utilize product bundling (e.g., frequently bought together items) and cross-selling/up-selling recommendations on product pages and during the checkout process.
Consider offering small incentives (e.g., a minor discount, a free sample) for exceeding specific order value thresholds.
Rationale: Increasing AOV directly boosts revenue without needing to increase the number of transactions. Strategies are generally feasible to implement.
Low Priority Recommendations
Refine Churn Prediction Approach (if needed):
Problem/Opportunity: The current churn prediction models were ineffective due to significant data imbalance in the target variable.
Action(s):
If accurate churn prediction remains a high business priority, apply resampling techniques (e.g., SMOTE for oversampling the minority class, or Undersampling) during model training to address the class imbalance.
Experiment with different classification algorithms or implement class weights within the models that are better suited for handling imbalanced datasets.
Explore and incorporate additional features that might be more predictive of churn, such as customer service interaction history, website browsing behavior, or engagement with marketing communications.
Rationale: Improving churn prediction accuracy requires significant technical effort to address data issues and potentially explore new features/models. Addressing the data issue in future purchase prediction and focusing on immediate retention actions are higher priorities with more certain short-term impacts.



Personal Financial Analysis
This project provides a comprehensive analysis of personal bank transactions, offering insights into spending habits, income vs expenses, and overall financial health.

Features
Data Loading and Overview: Loads bank transaction data and provides a summary of total transactions, date range, and current balance.
Spending Analysis: Visualizes spending distribution by category, monthly spending trends, top spending categories, and daily spending patterns.
Income vs Expense Analysis: Compares monthly income and expenses, shows net savings/loss by month, tracks account balance over time, and calculates the monthly savings rate.
Transaction Pattern Analysis: Identifies biggest expenses, analyzes spending by merchant, and detects unusual large transactions.
Personalized Financial Report: Generates a detailed report summarizing key financial metrics, providing a financial health score, and offering personalized recommendations.
Interactive Budget Tracker: Allows setting monthly budgets for different categories and compares them against actual spending.
Setup
Clone the repository (or download the notebook):

    pip install pandas numpy matplotlib seaborn
     
Requirement already satisfied: pandas in /usr/local/lib/python3.12/dist-packages (2.2.2)
Requirement already satisfied: numpy in /usr/local/lib/python3.12/dist-packages (2.0.2)
Requirement already satisfied: matplotlib in /usr/local/lib/python3.12/dist-packages (3.10.0)
Requirement already satisfied: seaborn in /usr/local/lib/python3.12/dist-packages (0.13.2)
Requirement already satisfied: python-dateutil>=2.8.2 in /usr/local/lib/python3.12/dist-packages (from pandas) (2.9.0.post0)
Requirement already satisfied: pytz>=2020.1 in /usr/local/lib/python3.12/dist-packages (from pandas) (2025.2)
Requirement already satisfied: tzdata>=2022.7 in /usr/local/lib/python3.12/dist-packages (from pandas) (2025.2)
Requirement already satisfied: contourpy>=1.0.1 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (1.3.3)
Requirement already satisfied: cycler>=0.10 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (0.12.1)
Requirement already satisfied: fonttools>=4.22.0 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (4.59.1)
Requirement already satisfied: kiwisolver>=1.3.1 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (1.4.9)
Requirement already satisfied: packaging>=20.0 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (25.0)
Requirement already satisfied: pillow>=8 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (11.3.0)
Requirement already satisfied: pyparsing>=2.3.1 in /usr/local/lib/python3.12/dist-packages (from matplotlib) (3.2.3)
Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.12/dist-packages (from python-dateutil>=2.8.2->pandas) (1.17.0)
Prepare your data:

The notebook expects a CSV file named bank_transactions.csv in the same directory as the notebook.
The CSV file should have the following columns: date, description, amount, category, and balance.
The provided notebook includes code to generate sample data if you don't have your own.
Run the notebook:

Execute each code cell in the notebook sequentially.
The notebook will output visualizations, summaries, and a personalized financial report.
Customization
Budgeting: You can modify the monthly_budgets dictionary in the create_budget_analysis function (in the "Interactive Budget Tracker" section) to set your own budget amounts for different categories.
Categorization: The categorize_transaction function (in the "Analyze Spending by Category" section) uses keywords to categorize transactions. You can modify this function to improve categorization based on your specific transaction descriptions.
Analysis Period: The analysis is based on the date range of the loaded data. Ensure your bank_transactions.csv file covers the period you want to analyze.
Dependencies
pandas
numpy
matplotlib
seaborn
These dependencies will be installed when you run the pip install command in the setup section.

License
MIT License

Contributing
I welcome contributions from the community! Whether it's fixing a bug, improving documentation, or suggesting a new feature/idea, your input helps make this project better.

Contact
daniel.o.nwanjah@gmail.com
+234 8066036369(whatsapp)
