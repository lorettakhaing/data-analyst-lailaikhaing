# data-analyst-lailaikhaing
Exploratory Data Analysis
Project Description: Exploratory Data Analysis (EDA) on City of Vancouver Parking Tickets Dataset
Project Title: City of Vancouver Parking Ticket: An Exploratory Data Analysis
Objective: The objective of this analysis is to investigate the factors contributing to the increase in water permit parking tickets issued in Vancouver from 2023 to 2024, focusing on whether additional streets were involved in ticket issuance in 2024. By comparing the distribution of tickets issued in 2023 and 2024 by street, the study aims to identify patterns or changes in street-level ticketing practices that could explain the observed increase.
Dataset: The Titanic dataset consists of passenger information from the ill-fated voyage of the RMS Titanic, including details such as:
•	Passenger ID: Unique identifier for each passenger
•	Survived: Survival status (0 = No, 1 = Yes)
•	Pclass: Passenger class (1st, 2nd, 3rd)
•	Name: Name of the passenger
•	Sex: Gender of the passenger
•	Age: Age of the passenger
•	SibSp: Number of siblings/spouses aboard
•	Parch: Number of parents/children aboard
•	Ticket: Ticket number
•	Fare: Fare paid by the passenger
•	Embarked: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

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
1. Data Ingestion
•	Objective: Upload and organize raw parking ticket data into AWS S3 for easy access and processing.
•	Steps:
1.	Created S3 buckets (pt-raw2-llk) to store the raw Excel data files.
2.	Structured the data with subfolders by quarter (ingestion_quarter=4) to accommodate updates and frequent access requirements.
3.	Configured storage class as S3 Standard to ensure high performance for analytics.
2. Data Profiling
•	Objective: Assess data quality, identify missing values, and gather descriptive statistics.
•	Steps:
1.	Created new buckets to store profiling results (pt-trf2-llk).
2.	Connected the dataset to AWS Glue DataBrew for profiling.
3.	Ran profiling jobs to analyze data quality and missing values for each column.
4.	Stored profiling results in designated subfolders.
3. Data Cleaning
•	Objective: Standardize and prepare data for transformation by addressing inconsistencies and missing information.
•	Steps:
1.	Created a new project in AWS Glue DataBrew for cleaning.
2.	Applied recipes to rename and standardize column names.
3.	Addressed null values and optimized dataset size using compression (Snappy format).
4.	Saved cleaned data in dedicated system and user subfolders in S3.

4. Data Pipeline Design
•	Objective: Transform and aggregate data for comparative analysis between 2023 and 2024.
•	Steps:
1.	Used AWS Glue Visual ETL for data transformation.
2.	Filtered data for 2023 and 2024 issued tickets separately.
3.	Aggregated ticket counts for each year, grouped by street.
4.	Renamed columns for clarity and consistency.
5.	Joined datasets for 2023 and 2024 on the street column to compare trends.
6.	Counted the total number of streets issuing tickets in each year.
7.	Saved the pipeline output into S3 for analysis.

5. Data Analysis
•	Objective: Compare ticket issuance trends between 2023 and 2024 and identify contributing factors.
•	Steps:
1.	Queried aggregated results in S3 using analytics tools.
2.	Examined the increase in total tickets and the number of streets involved.
3.	Identified correlations between street-level ticket counts in 2023 and 2024.
4.	Interpreted results to determine if new streets contributed to the increase in 2024.
6.Conclusion
The methodology integrates the systematic use of AWS services for robust data analysis. By comparing aggregated ticket data for 2023 and 2024, this approach identifies patterns or changes in street-level ticket issuance trends to address the research question effectively.

Tools and Technologies
The following tools and technologies were utilized to perform the analysis of parking ticket data for 2023 and 2024, ensuring efficient data management, processing, and analytics:

1. AWS Services
The Data Analytics Platform (DAP) leveraged several AWS components for scalable and robust data processing:
•	Amazon S3:
o	Raw Data Bucket: Stored the initial parking ticket dataset uploaded from local storage.
o	Transformed Data Bucket: Hosted cleaned and transformed datasets ready for analysis.
o	Curated Data Bucket: Stored analytics-ready datasets for final reporting and querying.
•	AWS Glue DataBrew:
o	Data Profiling: Used to examine dataset structure, detect missing values, and evaluate column-level data quality.
o	Data Cleaning: Applied recipes to clean, standardize, and prepare data for further transformations.
•	AWS Glue:
o	ETL (Extract, Transform, Load): Enabled complex transformations, column renaming, and aggregations. Managed the data pipeline, including filtering and joining datasets by street for year-over-year analysis.
•	AWS Query-in-S3 Functionality:
o	Used to query and analyze aggregated results directly from S3 buckets without exporting data to external tools.
Insights and Findings
From the analysis of parking ticket data for 2023 and 2024 in Vancouver, the following insights and findings were observed:
1. Increase in Ticket Issuance
•	The total number of parking tickets issued for water permits increased from 470 in 2023 to 634 in 2024, representing a 34.9% growth.
•	This increase highlights a shift in enforcement or changes in water permit violations.
2. Street-Level Analysis
•	The analysis identified an increase in the number of streets issuing tickets in 2024 compared to 2023. This suggests broader geographic coverage of ticket enforcement.
•	New streets in 2024 that were not present in the 2023 data contributed significantly to the rise in ticket issuance, indicating an expansion in the city’s monitoring or enforcement areas.
3. Correlation Between 2023 and 2024 Ticket Counts
•	A correlation analysis showed a moderate positive relationship between the number of tickets issued by streets in 2023 and 2024, indicating that many streets with high ticket counts in 2023 continued to have similar trends in 2024.
•	However, the presence of streets with zero tickets in 2023 but high counts in 2024 significantly influenced the overall increase.
4. Concentration of Tickets
•	The top 10 streets in 2024 accounted for a disproportionate percentage of tickets, similar to trends observed in 2023. This suggests that certain streets are consistently monitored or have higher rates of violations.
5. Possible Contributing Factors
•	Policy Changes: Potential changes in water permit policies or stricter enforcement might have led to higher ticket issuance.
•	Awareness Campaigns: Increased public awareness or complaints may have prompted enforcement in previously unmonitored streets.
•	Environmental Factors: Drought or water conservation measures in 2024 might have escalated ticketing to enforce regulations more rigorously.
6. Data Quality and Patterns
•	Missing values and inconsistencies in InfractionText were observed but addressed during the data cleaning process, ensuring accurate trend analysis.
•	The cleaned and aggregated data confirmed that geographic expansion (new streets) was a primary driver of the increase in ticket issuance.

