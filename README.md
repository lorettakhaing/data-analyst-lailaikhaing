**Projects **

**Project 1**
Exploratory Data Analysis

Project Description: Exploratory Data Analysis (EDA) on City of Vancouver Parking Tickets Dataset

Project Title: City of Vancouver Parking Ticket: An Exploratory Data Analysis

Objective: 
The objective of this analysis is to investigate the factors contributing to the increase in water permit parking tickets issued in Vancouver from 2023 to 2024, focusing on whether additional streets were involved in ticket issuance in 2024. By comparing the distribution of tickets issued in 2023 and 2024 by street, the study aims to identify patterns or changes in street-level ticketing practices that could explain the observed increase.

Dataset: 
The dataset contains information about parking tickets related to water permits issued in Vancouver for the years 2023 and 2024. It has 1,094 entries with the following columns:

•	Block: The block number where the infraction occurred.

•	Street: The name of the street where the ticket was issued.

•	EntryDate: The date the ticket was issued.

•	Bylaw: The bylaw code associated with the ticket.

•	Section: The specific section of the bylaw violated.

•	Status: The status of the ticket (e.g., issued).

•	InfractionText: A description of the infraction (e.g., "Manual watering of residential lawn").

•	Year: The year the ticket was issued.

•	BI_ID: A unique identifier for each ticket.

Exploratory Analysis Question

Are there more streets showing issued tickets in 2024 than in 2023?

This analysis aims to identify the correlation between the total number of issued tickets by street in 2023 and 2024 and determine whether additional streets contributed to the increase in ticket issuance in 2024.

Methodology:
Data Ingestion
Objective: Upload and organize raw parking ticket data into AWS S3 for easy access and processing.
Steps:
1.	Created S3 buckets (pt-raw2-llk) to store the raw Excel data files.
2.	Structured the data with subfolders by quarter (ingestion_quarter=4) to accommodate updates and frequent access requirements.
3.	Configured storage class as S3 Standard to ensure high performance for analytics.

Data Profiling
Objective: Assess data quality, identify missing values, and gather descriptive statistics.
Steps:
1.	Created new buckets to store profiling results (pt-trf2-llk).
2.	Connected the dataset to AWS Glue DataBrew for profiling.
3.	Ran profiling jobs to analyze data quality and missing values for each column.
4.	Stored profiling results in designated subfolders.

Data Cleaning
Objective: Standardize and prepare data for transformation by addressing inconsistencies and missing information.
Steps:
1.	Created a new project in AWS Glue DataBrew for cleaning.
2.	Applied recipes to rename and standardize column names.
3.	Addressed null values and optimized dataset size using compression (Snappy format).
4.	Saved cleaned data in dedicated system and user subfolders in S3.
   
Data Pipeline Design
Objective: Transform and aggregate data for comparative analysis between 2023 and 2024.
Steps:
1.	Used AWS Glue Visual ETL for data transformation.
2.	Filtered data for 2023 and 2024 issued tickets separately.
3.	Aggregated ticket counts for each year, grouped by street.
4.	Renamed columns for clarity and consistency.
5.	Joined datasets for 2023 and 2024 on the street column to compare trends.
6.	Counted the total number of streets issuing tickets in each year.
7.	Saved the pipeline output into S3 for analysis.

Data Analysis
Objective: Compare ticket issuance trends between 2023 and 2024 and identify contributing factors.
Steps:
1.	Queried aggregated results in S3 using analytics tools.
2.	Examined the increase in total tickets and the number of streets involved.
3.	Identified correlations between street-level ticket counts in 2023 and 2024.
4.	Interpreted results to determine if new streets contributed to the increase in 2024.

Conclusion

The methodology integrates the systematic use of AWS services for robust data analysis. By comparing aggregated ticket data for 2023 and 2024, this approach identifies patterns or changes in street-level ticket issuance trends to address the research question effectively.

Tools and Technologies

The following tools and technologies were utilized to perform the analysis of parking ticket data for 2023 and 2024, ensuring efficient data management, processing, and analytics:

AWS Services - The Data Analytics Platform (DAP) leveraged several AWS components for scalable and robust data processing:

Amazon S3

AWS Glue DataBrew

AWS Glue


Insights and Findings

From the analysis of parking ticket data for 2023 and 2024 in Vancouver, the following insights and findings were observed:
1. Increase in Ticket Issuance
   The total number of parking tickets issued for water permits increased from 470 in 2023 to 634 in 2024, representing a 34.9% growth.
   This increase highlights a shift in enforcement or changes in water permit violations.
2. Street-Level Analysis
The analysis identified an increase in the number of streets issuing tickets in 2024 compared to 2023. This suggests broader geographic coverage of ticket enforcement.
   New streets in 2024 that were not present in the 2023 data contributed significantly to the rise in ticket issuance, indicating an expansion in the city’s monitoring or enforcement areas.


