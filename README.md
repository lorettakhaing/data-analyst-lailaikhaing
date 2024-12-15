# Data Analytics Projects

## **Project 1: Exploratory Data Analysis**

### **Project Description**  
**Title:** City of Vancouver Parking Tickets: An Exploratory Data Analysis  

### **Objective**  
Investigate the factors contributing to the increase in water permit parking tickets issued in Vancouver from 2023 to 2024. The analysis focuses on determining whether additional streets were involved in ticket issuance in 2024 by comparing ticket distributions between the years.

### **Dataset**  
The dataset contains 1,094 entries of parking tickets related to water permits issued in Vancouver for 2023 and 2024 with the following columns:
- **Block:** Block number of the infraction.
- **Street:** Street name where the ticket was issued.
- **EntryDate:** Date the ticket was issued.
- **Bylaw:** Bylaw code associated with the ticket.
- **Section:** Specific section of the bylaw violated.
- **Status:** Status of the ticket (e.g., issued).
- **InfractionText:** Description of the infraction.
- **Year:** Year of ticket issuance.
- **BI_ID:** Unique identifier for each ticket.

### **Exploratory Analysis Question**  
Are there more streets issuing tickets in 2024 compared to 2023?

### **Methodology**
1. **Data Ingestion:**
   - Uploaded raw data into AWS S3 buckets structured by quarter.
   - Configured S3 storage class for performance and frequent access.

2. **Data Profiling:**
   - Used AWS Glue DataBrew to analyze data quality and identify missing values.
   - Stored profiling results in designated subfolders.

3. **Data Cleaning:**
   - Standardized column names and addressed null values.
   - Compressed data for optimized storage.

4. **Data Pipeline Design:**
   - Filtered and aggregated data for comparative analysis.
   - Merged 2023 and 2024 datasets to identify trends.

5. **Data Analysis:**
   - Queried aggregated results and analyzed ticket issuance trends.
   - Interpreted results to determine contributing factors for increased ticket issuance in 2024.

### **Tools and Technologies**
- **AWS S3:** Data storage and organization.
- **AWS Glue DataBrew:** Data profiling and cleaning.
- **AWS Glue:** Visual ETL for data transformation.

### **Insights and Findings**
1. **Increase in Ticket Issuance:**
   - Ticket issuance increased by 34.9% from 470 in 2023 to 634 in 2024.
2. **Street-Level Analysis:**
   - More streets issued tickets in 2024, indicating expanded geographic coverage.

**Design**
Draw io Diagram Data Analytic Platform (City of Vancouver – Domain- Parking Tickets) 

![image](https://github.com/user-attachments/assets/1afdcda7-8478-46e2-a617-6d2ccc2b115a)

---

## **Project 2: Descriptive Analysis**

### **Project Description**  
**Title:** Analyzing City of Vancouver's Enforcement of Water Conservation By-Law 12086

### **Objective**  
Analyze how the City enforces compliance with Water Conservation By-law 12086 by calculating the ticket issue rate for water permit-related tickets.

### **Dataset**
The dataset contains 367 entries with the following columns:
- **Block:** Block number of the infraction.
- **Street:** Street name where the ticket was issued.
- **EntryDate:** Date the ticket was issued.
- **Bylaw:** Bylaw code associated with the ticket.
- **Section:** Specific section of the bylaw violated.
- **Status:** Status of the ticket (e.g., Issued, Void, Warning).
- **InfractionText:** Description of the infraction (mostly null).
- **Year:** Year of ticket issuance.
- **BI_ID:** Unique identifier for each ticket.

### **Descriptive Analysis Question**
How does the City of Vancouver enforce compliance with Water Conservation By-law 12086?

### **Methodology**
1. **Data Ingestion:**
   - Uploaded raw data into AWS S3 and organized with lifecycle rules for cost optimization.

2. **Data Profiling:**
   - Analyzed data quality and missing values using AWS Glue DataBrew.

3. **Data Cleaning:**
   - Standardized columns and filled missing values.
   - Saved cleaned data in CSV and Parquet formats for efficient storage.

4. **Data Pipeline Design:**
   - Filtered and aggregated data by ticket statuses.
   - Calculated ticket issue rates and stored results in S3.

### **Tools and Technologies**
- **AWS S3:** Data storage and lifecycle management.
- **AWS Glue DataBrew:** Data profiling and cleaning.
- **AWS Glue ETL:** Visual ETL for data transformation and aggregation.

### **Insights and Findings**
1. **Enforcement of Water Conservation By-law:**
   - High ticket issue rates indicate active enforcement.
2. **Breakdown of Ticket Statuses:**
   - **Issued (IS):** Largest proportion, reflecting strict enforcement.
   - **Void (VA):** Possible errors or successful appeals.
   - **Warning (WR):** Educational measures for public awareness.
3. **Compliance Patterns:**
   - Geographic trends suggest potential hotspots of non-compliance.

### **Conclusion**
The findings reveal effective enforcement of water conservation regulations. However, targeted awareness campaigns and improved ticketing practices could further enhance compliance.

---

**Design**
Draw io Diagram Data Analytic Platform (City of Vancouver – Domain- Parking Tickets) 
 
![image](https://github.com/user-attachments/assets/9b74bb64-1973-437c-8e6f-5f83f65a9052)


## **Project 3: Diagnostic Analysis**

## Project Description  
**Diagnostic Analysis of Scholar Activity List at UCW Academic Office**  

## Project Title  
**Investigating Data Quality, Completeness, and Structure of UCW Scholar Activity Dataset**  

## Objective  
The primary goal is to identify any **anomalies, missing data, inconsistencies, or patterns** in the dataset that may impact its usability for:  
- Academic reporting  
- Visualization  
- Predictive modeling  
Insights from this analysis will inform necessary **data cleaning** and **transformation steps**, ensuring the dataset's readiness for downstream tasks.  

## Dataset Overview  
The dataset comprises details about scholarly activities conducted by faculty at UCW.  

### Dataset Fields:  
- **Faculty_ID**: ID of the faculty member  
- **Faculty_Name**: Name of the faculty member  
- **Department**: Faculty’s department  
- **Activity_Type**: Type of activity (e.g., Workshop, Research Paper)  
- **Activity_Title**: Title of the activity  
- **Year**: Year of the activity  
- **Scholarship_Type**: Type of scholarship (e.g., Application, Discovery, Teaching)  
- **Collaborators**: Collaborators involved in the activity  
- **Funding_Amount**: Funding amount received for the activity  
- **Status**: Status of the activity (e.g., In Review, Completed, Ongoing)  


## Methodology  

### Data Collection and Preparation  

#### **Data Generation**  
- **Simulation Design**:  
  - Dataset represents scholarly activities like publications, conferences, awards, and teaching engagements.  
  - Simulated data includes real-world attributes such as faculty names, departments, activity types, and statuses.  

- **Tool Used**:  
  - **ChatGPT**: Generated diverse, consistent, and realistic data entries.  

#### **Data Profiling**  
Conducted using **AWS Glue DataBrew** to assess data quality, structure, and completeness.  

### Step 1: Data Ingestion  
1. Uploaded the raw dataset to **Amazon S3** (bucket: `ac-sch-act-llk`).  
2. Connected the dataset to **AWS Glue DataBrew** for profiling.  

### Step 2: Profiling Job Setup  
- Created a profiling job in AWS Glue DataBrew for column-wise analysis.  
- Included all 10 columns:  
  - **String Columns** (8): Faculty_ID, Faculty_Name, Department, Activity_Type, Activity_Title, Scholarship_Type, Collaborators, Status  
  - **Integer Columns** (2): Year, Funding_Amount  

### Step 3: Profiling Insights  
1. **Data Quality**  
   - **Validity**: 100% valid values for all columns.  
   - **Missing Values**: None found (0% missing).  
   - **Outliers**: No outliers detected.  

2. **Value Distribution**  
   - **Distinct Values**:  
     - Faculty_ID: 50 unique values (high cardinality).  
     - Consistent uniqueness across other fields.  
   - **String Length**: Uniform distribution for text-based columns.  

3. **Top Distinct Values**  
   - Highlights the most frequent values in columns like Department and Activity_Type.  

### Step 4: Storage of Results  
- Stored profiling results in **Amazon S3** (`Data-Profiling` folder in bucket `ac-trf-llk`).  

### Step 5: Validation and Action Plan  
1. **Validation**:  
   - Dataset meets quality standards with no missing values or anomalies.  
   - Data aligns with the expected schema.  

2. **Action Plan**:  
   - No immediate cleaning required.  
   - Ready for downstream analysis (e.g., transformations, aggregations).  

## Outcome  
The UCW Scholar Activity dataset is **complete, valid, and ready** for analysis. The dataset requires no additional cleaning, ensuring a seamless transition to further analytical steps.  

## Tools and Technologies  

1. **AWS Glue DataBrew**  
   - **Purpose**: Automated profiling to assess dataset quality.  
   - **Key Features**:  
     - Data Quality Metrics: Valid, invalid, and missing values.  
     - Column Profiling: Unique values, distributions, and consistency checks.  
     - Insights Panel: Cardinality, outliers, and top distinct values.  

2. **Amazon S3**  
   - **Purpose**: Centralized storage for raw data and profiling results.  
   - **Key Features**:  
     - Raw Data Storage: Original dataset.  
     - Profiling Results: Stored in the `Data-Profiling` folder.  

## Deliverables  

1. **Data Profiling Report**  
   - Comprehensive report with:  
     - Data Quality Metrics  
     - Column Statistics (value distributions, string lengths)  
     - Schema Validation  

2. **Data Quality Insights**  
   - All columns validated with 100% valid data and no anomalies.  
   - High cardinality for Faculty_ID ensures unique identification.  

3. **Profiling Results Storage**  
   - S3 Folder: `Data-Profiling` within the `ac-trf-llk` bucket.  

4. **Data Visualization**  
   - Visual summaries generated by AWS Glue DataBrew:  
     - **Bar Charts**: Value distributions for key columns.  
     - **Top Distinct Values**: Most frequent values for each column.
**Design**

Draw io Diagram Data Analytic Platform (Scholar Activity UCW Dataset)

![image](https://github.com/user-attachments/assets/70a9bee4-f171-4c2f-9fa0-2917d15e5c1a)

Data Profiling Screen AWS Glue Brew

 ![image](https://github.com/user-attachments/assets/ed978229-7c9f-46a7-9a40-63f508e56032)

## Project 4: Data Wrangling

## **Project Title**
**Data Wrangling for Research List at UCW**


## **Objective**
The objective of this project is to perform comprehensive data wrangling on the **UCW Research List dataset** to ensure the data is clean, standardized, and structured for academic reporting and analysis. The process aims to address data inconsistencies, missing values, and formatting issues while transforming the dataset to derive meaningful insights, such as funding trends, research activity distributions, and departmental performance metrics. This ensures the dataset is optimized for efficient use in decision-making, visualization, and periodic updates.


## **Dataset**
The dataset contains information about research projects. Here are the key fields:

- **Research_ID**: Identifier for the research (String)  
- **Research_Title**: Title of the research (String)  
- **Faculty_Name**: Name of the faculty conducting the research (String)  
- **Department**: Department associated with the research (String)  
- **Year**: Year of the research (Integer)  
- **Research_Type**: Type of research (e.g., Quantitative Study, Literature Review) (String)  
- **Publication_Title**: Title of the related publication (String)  
- **Peer_Reviewed**: Whether the research is peer-reviewed (Yes/No) (String)  
- **Funding_Amount**: Amount of funding received (Integer)  
- **Status**: Status of the research (e.g., Completed, Ongoing) (String)  


## **Methodology**

### **Step 1: Data Ingestion**
1. **Raw Data Storage**:
   - Uploaded the raw dataset to **Amazon S3** in the `ac-raw-llk` bucket.
   - Organized data using a folder structure (e.g., academic years) for easy access.
2. **Configuration**:
   - Stored raw data with metadata, such as `Department`, `Research_Type`, and `Activity_Period`.
   - Assigned the **S3 Standard** storage class to ensure high performance for active data.


### **Step 2: Data Profiling**
1. **Profiling Job**:
   - Created a profiling job (`ac-prf-job-llk`) in **AWS Glue DataBrew** to evaluate the raw data.
   - Generated insights into:
     - Null and missing values.
     - Data type inconsistencies.
     - Frequency distributions for categorical columns.
2. **Key Findings**:
   - Detected columns with inconsistent formats (e.g., dates).
   - Identified missing values in `Research_Title` and `Funding_Amount`.


### **Step 3: Data Cleaning**
1. **Cleaning Job**:
   - Created a cleaning project (`ac-clnstr-job-llk`) in **AWS Glue DataBrew**.
   - Applied transformations, such as:
     - **Standardizing Column Names**: Renamed columns to adhere to a consistent naming convention.
     - **Filling Missing Values**:
       - Replaced missing categorical values with "Not Specified."
       - Imputed missing numeric values (e.g., funding amounts) using the median of relevant groups.
     - **Date Formatting**: Standardized dates to `YYYY-MM-DD` format.
2. **Output Storage**:
   - Saved cleaned data in the `ac-trf-llk` bucket:
     - **CSV** format for user accessibility.
     - **Parquet** format (with Snappy compression) for efficient storage and querying.

### **Step 4: Data Transformation**
1. **ETL Pipeline**:
   - Built an **AWS Glue ETL job** (`ac-res-etl-llk`) for advanced transformations:
     - Filtered data by `Year` and `Department`.
     - Aggregated funding data to calculate totals and averages by department and activity type.
     - Derived new columns (e.g., `Research_Duration` and `Activity_Category`).
2. **Output Storage**:
   - Transformed data was stored in **S3** (`ac-trf-llk`) for further reporting and visualization.


### **Step 5: Data Validation**
1. **Validation Job**:
   - Ran a final data profiling job to ensure all cleaning and transformations were applied correctly.
   - Verified the integrity of cleaned and transformed data.


## **Tools and Technologies**

### **AWS Tools Used**
1. **Amazon S3**:
   - Centralized storage for raw, cleaned, and transformed data.
   - Lifecycle rules to archive inactive data.
2. **AWS Glue DataBrew**:
   - Data profiling and cleaning jobs to standardize and validate the dataset.
3. **AWS Glue (ETL Jobs)**:
   - Built advanced ETL pipelines for filtering, aggregations, and data transformations.

## **Deliverables**

1. **Cleaned Dataset**  
   - A cleaned and standardized version of the UCW Research List dataset stored in:
     - **CSV** format for ease of access.
     - **Parquet** format for optimized storage and querying.

2. **Transformed Dataset**  
   - Aggregated and derived metrics stored in S3 for reporting, such as:
     - Total and average funding by department.
     - Research activity trends over time.

3. **Data Profiling Reports**  
   - Reports generated by **AWS Glue DataBrew**, detailing:
     - Data quality metrics.
     - Distribution of values for key columns.
     - Anomalies and missing data.

4. **ETL Pipeline**  
   - An **AWS Glue ETL pipeline** that automates the transformation of research data, enabling efficient reuse for periodic updates.

**Design**

Draw io Diagram Data Analytic Platform (Research List UCW Dataset)

![image](https://github.com/user-attachments/assets/31d2c40e-4e9e-482a-ba9d-7b41df2085d4)

## **Conclusion**
This project establishes a robust workflow for wrangling research data, ensuring it is analysis-ready and aligned with academic reporting requirements. By leveraging AWS tools, the process ensures scalability, efficiency, and reliability for managing research activity data at UCW.

## Project 5: Data Quality

**Project Title:**  

### Data Quality Control for the City of Vancouver Parking Ticket Dataset 

**Project Description:**  
The project integrates data quality control measures within a robust data pipeline hosted on AWS, designed for the City of Vancouver Parking Ticket dataset. The system ensures the reliability, accuracy, and consistency of the dataset, leveraging scalable cloud-based services to streamline data ingestion, transformation, validation, and monitoring.


### Data Pipeline Overview
Based on the provided architecture diagram, the data pipeline for the parking ticket dataset is structured as follows:

#### **1. Data Ingestion and Storage**
- **Source:** The data team accesses parking ticket data via the internet, which is stored in **Amazon S3** buckets (`pt-tr2-llk`).
- **Security:** Data is encrypted using AWS Key Management Service (KMS) with `pt-st-key-llk` for secure storage.


#### **2. ETL Processing**
- **AWS Glue Jobs:**  
  - Multiple AWS Glue jobs are orchestrated for ETL tasks:
    - Extract raw data from S3 buckets.
    - Transform the data by removing duplicates, standardizing formats, and imputing missing values.
    - Load the cleansed data back into S3 (`pt-st-datacatalog-llk`) for further analysis.

- **Transformation Logic:**  
  - Applied using AWS Glue transformations to adhere to predefined data quality rules.

#### **3. Data Cataloging and Querying**
- **AWS Glue Data Catalog:**  
  - Metadata is maintained in AWS Glue's Data Catalog (`pt-st-datacatalog-llk`) to ensure seamless integration with analytics tools.  
  - This enables efficient querying and exploration of structured datasets.

- **Amazon Athena:**  
  - Utilized to run SQL queries on the cleansed data stored in S3.  
  - Queries validate data quality metrics (e.g., uniqueness, completeness) and generate analytical insights.

#### **4. Validation and Reporting**
- **SQL Query Outputs:**  
  - Query results are validated against predefined KPIs and metrics (e.g., missing value rate <5%, duplicates = 0).  
  - Outputs are stored in a secondary S3 bucket (`pt-cur-llk`).

#### **5. Monitoring and Security**
- **Amazon CloudWatch:**  
  - Real-time monitoring of data pipeline activities.  
  - Tracks ETL job status, error logs, and overall data quality trends.

- **Amazon CloudTrail:**  
  - Auditing is implemented to track access and changes to the data pipeline.  

- **KMS Integration:**  
  - Ensures data at rest and in transit is encrypted, maintaining security compliance.

#### **6. Dashboard and Reporting**
- **Visualization Tools:**  
  - A dashboard (`pt-st-DAP-Dash-llk`) is implemented to provide insights into data quality metrics, job execution status, and KPIs.

### Data Quality Control Measures (Detailed Implementation)
**1. Current State Assessment:**  
   - Identified data inconsistencies during ingestion (e.g., missing fields and invalid formats).  
   - Integrated monitoring tools to log pipeline performance and highlight irregularities.  

**2. Data Profiling:**  
   - AWS Glue Data Catalog provides metadata profiling for fields such as ticket ID, timestamps, and fine amounts.  

**3. Data Cleansing:**  
   - SQL scripts and Glue transformations remove duplicates, correct invalid data, and standardize field formats (e.g., date to ISO 8601).  

**4. Validation Rules:**  
   - Athena SQL queries check data integrity post-transformation:
     - Ticket IDs are unique.
     - Fine amounts are within valid ranges.
     - Missing critical fields are flagged for manual review.  

**5. Monitoring and Reporting:**  
   - CloudWatch dashboards offer real-time monitoring of ETL jobs.  
   - Alerts are configured for anomalies like job failures or data deviations.

### Deliverables
- A secure and reliable data pipeline for the parking ticket dataset.  
- Real-time dashboard visualizing data quality metrics and trends.  
- Comprehensive documentation of the ETL process and validation framework.  
- Cleaned and validated dataset ready for analysis and reporting.  

**Design**

Draw io Diagram Data Analytic Platform (City of Vancouver - Parking Tikcet Dataset )
![image](https://github.com/user-attachments/assets/48f9b66c-9596-45af-9292-b2b310ea3be4)







