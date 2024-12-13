#   Extended Hospitalizations Exploratory Data Analysis

## Rationale
As a current clinician in a rehabilitation hospital, I have seen and treated many patients who have experienced acute illnesses that require prolonged hospitalizations. Due to the severity of their conditions, most of these patients suffer from life-changing and life-long impairments. Frequently, these conditions are a result of chronic illnesses, however the cases I find most poignant are those that appeared to be healthy and independent previous to the illness. The aim of this analysis is to explore data from hospital stays, including primary diagnosis and demographic information to discover any underlying correlations of extended stays compared to ‘average’ stays. In addition, I am interested in the significant financial impact of these stays and any relevant findings related to charges vs costs. 

## Research
Prior to analyzing data and drawing conclusions, research needed to be conducted to reflect established norms. According to Doctoroff & Herzig (2020) extended hospitalizations are defined to be 21 days or longer. Freeman et al. (2018) found that the statistical average hospitalization to be 4.6 days. This project will base analysis on an ‘average’ hospital stay to be between 4 and 5 days and ‘extended’ stay as treated than 21 days to reflect these sources

## Data Sources 
The hospital data is sourced from New York State Department of Health in the years 2015 and 2021. Inpatient hospital data had been previously de-identified according to HIPAA guidelines and includes information of patient characteristics, diagnoses, charges, costs, etc for every hospital stay in the state of New York in these two years. Given the enormity of the data (2.35 million rows for 2015 and 2.13 million for 2021), results queried were limited to 10,000 rows for each year of data. 

 
## Data Processing and Data Transformation
Hospital data for years 2015 and 2021 were returned as JSON from API and converted into Python dictionaries by sodapy. The datasets were then concatenated and cleaned using pandas. A new column was created to calculate the charges to costs ratio. The data was then filtered and separated into two CSV files: an average hospitalization of 4-5 days and extended hospitalization of greater than or equal to 21 days. For each new set of data, diagnoses were filtered for relevance. Finalized data was analyzed and displayed with a Tableau dashboard.

## Running the Project
1. Clone the repository to your machine:
    ```git clone https://github.com/ChloeSecreti/Healthcare-Data-Analysis
        ```

2. Create and activate a virtual environment, and install required packages from 'requirements.txt':
- **Linux/Mac:**
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  pip install -r requirements.txt
  ```
- **GitBash:**
  ```bash
  python -m venv venv
  source venv/Scripts/activate
  pip install -r requirements.txt
  ```
3. Once complete, be sure to deactivate:
    ```
    deactivate
      ```

## Key Findings and Visualization





## Resources
Doctoroff L, Herzig SJ. Predicting Patients at Risk for Prolonged Hospital Stays. Med Care. 2020 Sep;58(9):778-784. doi: 10.1097/MLR.0000000000001345. PMID: 32826743; PMCID: PMC7444462.

Freeman WJ (AHRQ), Weiss AJ (IBM Watson Health), Heslin KC (AHRQ). Overview of U.S. Hospital Stays in 2016: Variation by Geographic Region. HCUP Statistical Brief #246. December 2018. Agency for Healthcare Research and Quality, Rockville, MD. www.hcup-us.ahrq.gov/reports/statbriefs/sb246-Geographic-Variation-Hospital-Stays.pdf.


