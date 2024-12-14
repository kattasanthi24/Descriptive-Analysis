# **Project-1: Data Analysis of Public Art Installations**

---

## **Project Title**
**Descriptive Analysis of Public Art Installations**

---

## **Project Description**
This project aims to analyze the annual trends in public art installations, focusing on identifying patterns over time and establishing an efficient pipeline for data analysis and processing. The workflow integrates **AWS Services** and **Draw.io** for process visualization and automation.  

The data is managed on **Amazon S3** with the following structure:  
- **`pub-arts-raw-san`**: Stores the raw dataset.  
- **`pub-arts-trf-san`**: Stores the transformed and cleaned dataset.  

AWS Glue services, including **DataBrew** and **ETL Pipelines**, are utilized for data profiling, cleaning, sensitive data masking, and automation.

---

## **Objective**
To analyze public art installations over the years, identify trends, and implement a robust data pipeline for efficient analysis and processing.

---

## **Dataset Details**
The dataset includes the following columns:  
- **Title of Work**: The name of the public art installation.  
- **Material Used**: The materials used in the artwork (e.g., metal, wood).  
- **Neighborhood**: The neighborhood where the installation is located.  
- **Year of Installation**: The year the art was installed.  
- **Artist Name**: The name of the artist who created the work.  
- **Status**: Current status of the installation (e.g., Active, Removed).  
- **Description**: Brief description of the art installation.  
- **Coordinates**: Latitude and longitude of the installation location.  

---

## **Methodology**

### **1. Data Ingestion**
The raw dataset is uploaded to the S3 bucket `pub-arts-raw-san`. This follows AWS best practices for scalability and cost-effectiveness.  

- **S3 Bucket Structure:**  
  1. **`pub-arts-raw-san`**: Contains raw data files.  
  2. **`pub-arts-trf-san`**: Stores cleaned and transformed data.  

![image](https://github.com/user-attachments/assets/404ae9e9-9463-4e47-866f-11f7064f95d8)

---

### **2. Data Profiling**
Data profiling ensures the dataset’s structure, accuracy, and quality.  

- **Process:**  
  1. Connected the raw dataset from `pub-arts-raw-san` to AWS Glue DataBrew.  
  2. Ran profiling jobs to evaluate:  
     - Missing values  
     - Accuracy of data  
     - Overall data quality  

![image](https://github.com/user-attachments/assets/f43ef7b6-0ebd-49da-8e72-6c1fd02629ec)  

**Key Insights from Profiling:**  
- Missing values observed in **Material Used** (5%) and **Description** (10%).  
- Critical fields identified: **Year of Installation**, **Neighborhood**, and **Title of Work**.  

---

### **3. Data Cleaning**
Data cleaning focuses on removing inconsistencies and preparing the dataset for analysis.  

- **Steps:**  
  1. Removed irrelevant entries and special characters.  
  2. Filtered essential columns:  
     - **Title of Work**  
     - **Material Used**  
     - **Neighborhood**  
     - **Year of Installation**  
  3. Filled missing values in **Material Used** with "Mixed Media" and **Description** with "Not Available."  
  4. Exported cleaned data in the following formats:  
     - **Parquet File**: For optimized storage and faster processing.  
     - **CSV File**: User-friendly format filtered by year and material type.  

![image](https://github.com/user-attachments/assets/486d7264-7c5b-4b2f-a781-a642bca65b32)  

---

### **4. Data Pipeline Design**
An **AWS Glue ETL Pipeline** was created to automate and standardize the data transformation process.  

- **Pipeline Features:**  
  1. Data completeness checks to ensure no critical fields are blank.  
  2. Sensitive data compliance with Canadian privacy regulations.  
  3. Trend analysis of public art installations by year.  

![image](https://github.com/user-attachments/assets/97ee9336-6537-4c9b-ac95-1204e5e3e1e1)  

---

## **Tools and Technologies**
1. **AWS S3**: For data storage and management.  
2. **AWS Glue DataBrew**: For data profiling and cleaning.  
3. **AWS Glue ETL Pipeline**: For data transformation and automation.  
4. **Draw.io**: For creating process diagrams and visual representations.  

---

## **Deliverables**
1. **Data Insights:** Annual trends in public art installations.  
2. **Processed Dataset:** Cleaned and structured data ready for analysis.  
3. **ETL Pipeline:** Automated pipeline for future datasets.  
4. **Compliance and Audit:** Report ensuring adherence to data protection regulations.  

---

## **Conclusion**
This project successfully analyzes public art installations, identifies annual trends, and creates a reusable pipeline for future data. The integration of AWS services ensures scalability, efficiency, and compliance.  

---
