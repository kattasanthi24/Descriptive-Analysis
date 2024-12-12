# project-1

# Descriptive Analysis

## Project Description:
This project focuses on analyzing the annual number of public art installations and observing trends over time. Using **Draw.io**, I designed a diagrammatic representation of the entire process. Data is managed and stored on **Amazon S3** using the following structure:  
- `pub-arts-raw-san`: For storing the raw dataset.  
- `pub-arts-trf-san`: For storing the transformed and cleaned dataset.  

**AWS Glue DataBrew** is used for assessing and cleaning the dataset, while an **AWS Glue ETL Pipeline** ensures efficient automation, including sensitive data masking and transformation.

---

## Project Title:
Data Analysis of Public Art Installations

---

## Objective:
To study and analyze the number of public art installations annually, identify trends, and create an efficient pipeline for data analysis and processing.

---

## Dataset:
The dataset includes details such as:  
- Title of Work  
- Material Used  
- Neighborhood  
- Year of Installation  

---

## Methodology:

### **Step 1: Data Ingestion**  
The raw dataset was uploaded to the S3 bucket `pub-arts-raw-san`. This straightforward method follows AWS best practices, ensuring cost-effectiveness and scalability.  
- **Bucket Structure:**  
  1. `pub-arts-raw-san`: Stores raw data.  
  2. `pub-arts-trf-san`: Stores transformed and cleaned data for further processing.

![image](https://github.com/user-attachments/assets/404ae9e9-9463-4e47-866f-11f7064f95d8)

### **Step 2: Data Profiling**  
Data profiling involves evaluating the dataset's structure, accuracy, and relationships.  
- **Process:**  
  1. Connected the dataset in `pub-arts-raw-san` to AWS Glue DataBrew.  
  2. Ran a profiling job to identify missing values, accuracy, and overall data quality.  

![image](https://github.com/user-attachments/assets/f43ef7b6-0ebd-49da-8e72-6c1fd02629ec)

### **Step 3: Data Cleaning**  
Key cleaning activities include:  
1. Removed irrelevant entries and special characters.  
2. Filtered columns like `Title of Work`, `Material Used`, `Neighborhood`, and `Year of Installation`.  
3. Filled nullable fields with "Mixture of All Elements" to ensure no empty fields remain.

Outputs:  
- **Parquet File:** Optimized for storage and processing.  
- **CSV File:** User-friendly format filtered by `Year of Installation` and `Type of Material Used`.

![image](https://github.com/user-attachments/assets/486d7264-7c5b-4b2f-a781-a642bca65b32)

### **Step 4: Data Pipeline Design**  
An **ETL Pipeline** was created using AWS Glue to automate and standardize data transformation.  
- **Checks Performed:**  
  1. **Data Completeness:** Ensured no critical fields are left blank.  
  2. **Sensitive Information Compliance:** Verified adherence to Canadian legislation for data protection.

![image](https://github.com/user-attachments/assets/97ee9336-6537-4c9b-ac95-1204e5e3e1e1)


---

## Tools and Technologies:
1. **AWS S3**: Data storage and management.  
2. **AWS Glue DataBrew**: Data profiling and cleaning.  
3. **AWS Glue ETL Pipeline**: Data transformation and automation.  
4. **Draw.io**: Process diagram creation.  

---

## Deliverables:
1. **Data Insights:** Annual trends in public art installations.  
2. **Processed Dataset:** Cleaned, structured data ready for analysis.  
3. **ETL Pipeline:** Automated and reusable for future datasets.  
4. **Compliance and Audit:** Sensitive data compliance report and audit trail.  

