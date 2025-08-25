# Data_Science-Portfolio
This Repo contains 12 projects that demonstrate my end-to-end data science knowledge and skills

Data Quality Analysis and Reporting Tool
This project provides a basic set of tools for analyzing data quality issues within a dataset. It includes functions for detecting missing data, outliers, duplicates, and consistency problems, and generates both a detailed text report and a visual dashboard.

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


     
COVID-19 Data Explorer
Project Description
I created this project explore and visualize global COVID-19 data using Python, and also leveraging the power of pandas for data manipulation, plotly for interactive visualizations, and streamlit to build an interactive web application. I downloaded the latest COVID-19 data from Our World in Data and performed cleaning, preparation, and various analytical tasks to understand trends, country comparisons, vaccination progress, and correlations with demographic factors.

Setup and Installation
in other to run this project, you will need a Python environment with the necessary libraries installed. As far as i know, The easiest way to get started is by using Google Colaboratory (Colab), which provides a free, cloud-based Jupyter notebook environment.

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
