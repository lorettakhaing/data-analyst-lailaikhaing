**Data Analytics Projects**


**Project 1**
**Exploratory Data Analysis**

Project Description: Exploratory Data Analysis (EDA) on City of Vancouver Parking Tickets Dataset

Project Title: City of Vancouver Parking Ticket: An Exploratory Data Analysis

**Objective:**

The objective of this analysis is to investigate the factors contributing to the increase in water permit parking tickets issued in Vancouver from 2023 to 2024, focusing on whether additional streets were involved in ticket issuance in 2024. By comparing the distribution of tickets issued in 2023 and 2024 by street, the study aims to identify patterns or changes in street-level ticketing practices that could explain the observed increase.

**Dataset:** 
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

Draw io Diagram Data Analytic Platform (City of Vancouver – Domain- Parking Tickets) 

![image](https://github.com/user-attachments/assets/1afdcda7-8478-46e2-a617-6d2ccc2b115a)


**Exploratory Analysis Question**

Are there more streets showing issued tickets in 2024 than in 2023?

This analysis aims to identify the correlation between the total number of issued tickets by street in 2023 and 2024 and determine whether additional streets contributed to the increase in ticket issuance in 2024.

**Methodology:**

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


**Tools and Technologies**

The following tools and technologies were utilized to perform the analysis of parking ticket data for 2023 and 2024, ensuring efficient data management, processing, and analytics:

AWS Services - The Data Analytics Platform (DAP) leveraged several AWS components for scalable and robust data processing:

Amazon S3

AWS Glue DataBrew

AWS Glue

**Insights and Findings**

From the analysis of parking ticket data for 2023 and 2024 in Vancouver, the following insights and findings were observed:
1. Increase in Ticket Issuance
   The total number of parking tickets issued for water permits increased from 470 in 2023 to 634 in 2024, representing a 34.9% growth.
   This increase highlights a shift in enforcement or changes in water permit violations.
2. Street-Level Analysis
The analysis identified an increase in the number of streets issuing tickets in 2024 compared to 2023. This suggests broader geographic coverage of ticket enforcement.
   New streets in 2024 that were not present in the 2023 data contributed significantly to the rise in ticket issuance, indicating an expansion in the city’s monitoring or enforcement areas.


**Project 2**

**Descriptive Analysis**

Project Description: Descriptive Analysis of City of Vancouver Parking Tickets 

Project Title: Analyzing City of Vancouver enforces compliance with Water Conservation By-Law 1206.

Objective: The goal of this descriptive analysis is to determine how the City of Vancouver enforces compliance with the Water Conservation By-law (By-law 12086). Specifically, the analysis focuses on calculating the ticket issue rate for water permit-related tickets. This will provide insight into the proportion of tickets issued relative to all tickets processed under different statuses (Issued, Void, Warning).

**Dataset**: 

The dataset contains information about parking tickets issued in Vancouver for water conservation enforcement in 2024. It includes 367 entries with the following columns:

•	Block: The block number where the infraction occurred.
•	Street: The street name where the ticket was issued.

•	EntryDate: The date the ticket was issued.

•	Bylaw: The bylaw code associated with the ticket.

•	Section: The specific section of the bylaw violated.

•	Status: The status of the ticket (e.g., Issued (IS), Void (VA), Warning (WR)).

•	InfractionText: Descriptive text for the infraction (mostly null in this dataset).

•	Year: The year the ticket was issued.

•	BI_ID: A unique identifier for each ticket.

The dataset contains all required information to calculate the ticket issue rate for water permit tickets based on the provided formula.
Missing values are notable in the InfractionText column, with only 64 non-null entries out of 367 total records.

Draw io Diagram Data Analytic Platform (City of Vancouver – Domain- Parking Tickets) 
 
![image](https://github.com/user-attachments/assets/9b74bb64-1973-437c-8e6f-5f83f65a9052)

**Descriptive Analysis Question**

How does the City of Vancouver enforce compliance with the Water Conservation By-law (By-law 12086)?

**Methodology**

Step 1: Data Ingestion

Objective: Upload raw parking ticket data to AWS S3 and organize for further processing.

•	Created an S3 bucket named pt-raw-llk for storing raw data.

•	Structured the data by creating a subfolder ingestion_quarter=4 to accommodate quarterly updates.

•	Uploaded the parking_tickets_20241124.xlsx file containing 367 records.

•	Configured S3 storage with lifecycle rules to optimize costs:
   Move to Glacier Flexible Retrieval after 90 days.
   Move to Glacier Deep Archive after 180 days.
   
Step 2: Data Profiling

Objective: Assess data quality and identify issues for cleaning.

•	Created a profiling dataset in AWS Glue DataBrew (pt-raw-dataset-llk) to analyze the raw data.

•	Ran a profiling job, detecting null values in some columns.

•	Stored profiling results in a dedicated Data-Profiling folder within the S3 bucket.

Step 3: Data Cleaning

•	Objective: Standardize and clean data for analysis.

•	Renamed columns for consistency and filled missing values (e.g., "Not Applicable" for Infraction_Text).

•	Partitioned outputs by block and saved cleaned data in CSV and Snappy-compressed Parquet formats for optimized storage.

•	Stored cleaned data in Data-Cleaning folders within S3 for user and system access.

Step 4: Data Pipeline Design

Objective: Calculate ticket issue rates and store the results.

•	Designed a Visual ETL pipeline in AWS Glue:

1.	Extracted cleaned data from S3.
2.	Filtered rows with specific statuses (IS, VA, WR).
3.	Aggregated counts for:Total tickets with Issued (IS) status.Total tickets with statuses IS, VA, and WR.
4.	Used derived column functionality to calculate ticket issue rates.
5.	Saved results in the Valid-Ticket-Issue-Rate folder, in CSV (User) and Parquet (System) formats.

**Tools and Technologies**

•  Amazon S3:
   Stores raw, transformed, and curated parking ticket datasets.
   
   Configured lifecycle rules for cost optimization (e.g., Glacier storage tiers).
   
•  AWS Glue DataBrew

   Profiles raw data to identify missing values and assess data quality.
   
   Cleans and standardizes datasets for further analysis.
•  AWS Glue ETL

   Builds a Visual ETL pipeline for transformations, aggregations, and joins.
   
   Calculates ticket issue rates using derived columns.
   
**Insights and Findings**

The descriptive analysis of parking ticket data for water permits in Vancouver, focusing on the compliance with the Water Conservation By-law (By-law 12086), yielded the following insights:


1. Enforcement of Water Conservation By-law
   
•	The ticket issue rate provides a quantitative measure of how effectively the City enforces compliance with water permit regulations.

•	The high proportion of tickets with Issued (IS) status indicates that enforcement efforts are active and consistent.


2. Breakdown of Ticket Statuses
   
•	Issued (IS): Represents the largest proportion of tickets, demonstrating strict enforcement of violations.

•	Void (VA): Indicates instances where tickets were invalidated, potentially due to errors or successful appeals.

•	Warning (WR): Suggests an emphasis on educating the public about water permit compliance, serving as a proactive measure.


3. Compliance Patterns
   
•	High Ticket Issue Rate: Indicates robust enforcement mechanisms but may also reflect frequent non-compliance.

•	Geographic Trends: Further analysis could reveal hotspots of non-compliance, enabling targeted enforcement or public awareness campaigns.


Conclusion
The findings indicate that the City of Vancouver is actively enforcing water conservation regulations, as reflected in the high ticket issue rate. While the enforcement mechanism appears effective, there is room for improvement through targeted awareness efforts and refining ticket issuance practices to enhance compliance further

   



