#   Extended Hospitalizations Exploratory Data Analysis
<img src="https://post.medicalnewstoday.com/wp-content/uploads/sites/3/2023/08/patient-ward-hospital-delirium-1296x728-header-1024x575.jpg" width="700" height="300">

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
    ```git clone https://github.com/ChloeSecreti/Healthcare-Data-Analysis```

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

I used a Tableau Dashboard to visualize my data. The dashboard allows the user to use a filter to compare average and extended hospitalization data. In the first image, the tables are displaying results for extended stays. The second image represents the average stay data.

Link to dashboard: https://public.tableau.com/app/profile/chloe.secreti/viz/ExtendedvsAverageHospitalization/Dashboard1

<img src="/Users/chloeburrell/Documents/Projects/Healthcare-Data-Analysis/ReadMe_Images/Extended_Hospializations_Dashboard.png" width="800" />

<img src="/Users/chloeburrell/Documents/Projects/Healthcare-Data-Analysis/ReadMe_Images/Average_Hospitalizations_Dashboard.png" width="800" />

## Interpretation 
Regarding diagnoses, both sets show sepsis as most common diagnosis. Sepsis was particularly frequent in extended hospitalizations, accounting for the vast majority of diagnoses. COVID-19 also accounted for a high number of cases in both lengths of stay. The data suggests that chronic conditions such as COPD, Congestive Heart Failure, and Osteoarthritis are associated with shorter lengths of stays while acute illnesses such as Cerebral Infarction and Respiratory failure are associated with extended stays.  

One of the most striking results is the the table showing cost to charge ratio in different lengths of stays. Among extended hospitalizations, the median ratio varied from as high as 6.5 (at 57 days) to a low a 1.3 (for 99 days). Average stays show a median of 1.9. These findings, which could be due to a wide range of factors, suggest a lack of standard practices for those that stay 21+ days with charges far exceeding costs. This data could be useful for those attempting to negotiate charges with hospitals. 

Demographic information related to age, race, and gender demonstrated some interesting findings. In particular, the portion of men to women reversed for length of stay; women were the majority for average hospitalizations and men for extended stays. Extended hospitalizations show an increased proportion of "other race" and also Spanish/Hispanic. 

## Conclusion 
This project focused on exploratory analysis of extended hospitalizations compared to average stays. Some key takeaway include chronic conditions are less common as the primary diagnosis of prolonged hospitalizations, while acute illnesses are much more common. Demographics including males, Spanish/Latino, and those of "other race" (not identifying as white/black) showed an increase compared to average stays. This information could be built upon by taking into consideration the scientific research already conducted on demographics of particular health conditions and comparing it to prolonged hospital stays. 

This project was limited in the amount of data analyzed, the geographic location (exclusively from the state of New York), the diagnoses included (showing primary diagnosis only), among many other variables which are often inherent in health data. As medicine, technology, data analytics, and predictive modeling advance, it is conceivable that expensive, life-changing hospitalizations may decrease. 

## Resources
Doctoroff L, Herzig SJ. Predicting Patients at Risk for Prolonged Hospital Stays. Med Care. 2020 Sep;58(9):778-784. doi: 10.1097/MLR.0000000000001345. PMID: 32826743; PMCID: PMC7444462.

Freeman WJ (AHRQ), Weiss AJ (IBM Watson Health), Heslin KC (AHRQ). Overview of U.S. Hospital Stays in 2016: Variation by Geographic Region. HCUP Statistical Brief #246. December 2018. Agency for Healthcare Research and Quality, Rockville, MD. www.hcup-us.ahrq.gov/reports/statbriefs/sb246-Geographic-Variation-Hospital-Stays.pdf.


