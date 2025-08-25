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
