# Data Analytics Projects
---

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

**Visualizations**
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

**Visualizations**
Draw io Diagram Data Analytic Platform (City of Vancouver – Domain- Parking Tickets) 
 
![image](https://github.com/user-attachments/assets/9b74bb64-1973-437c-8e6f-5f83f65a9052)

---

