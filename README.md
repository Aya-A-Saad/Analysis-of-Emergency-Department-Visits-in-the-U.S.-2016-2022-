 # **Project Title**  
Healthcare Utilization Trends: An Analysis of Emergency Department Visits in the U.S. (2016–2022)

## **Problem Statement**  
Emergency departments (EDs) in the U.S. are essential for urgent care, but their usage patterns have shifted significantly during recent years—especially around the COVID-19 pandemic. Understanding healthcare utilization trends and these shifts is crucial for improving public health responses and resource planning.

This project uses data from 2016–2022, with 2022 as the baseline year for comparison.

## **Data Source**  
Source: Centers for Disease Control and Prevention (CDC)  

Data description: The original dataset contains **6,777 rows** and **12 variables**. After cleaning (removing null or redundant values), the final analysis was conducted on **5,913 rows**.  
Each row represents a combination of **year, diagnosis/reason for visit, demographic subgroup, and estimate type** (count or rate, normalized for proportional comparison). The data spans **2016 to 2022**, covering the **10 leading primary diagnoses** and **10 leading reasons for ED visits** in the U.S.

## **Tools & Technologies Used**  
- Python 3 (Google Colab environment) with pandas, numpy, matplotlib,seaborn and scipy

## **Methodology**  

- **Data Cleaning:** Removed rows where the 'Reliable' column was marked 'No'.  
  Example code:  
  ```python
  df = df.drop(df[df['Reliable'] == 'No'].index)
  ```
 - **Analysis Techniques:**

1. Confidence Interval Width Analysis to filter reliable estimates based on CI width percentage (threshold set at 15%).

2. Statistical Significance Testing using overlapping confidence intervals to identify significant changes.

## **Findings**

### 1. Overall ED Utilization Trends

* **2018** visits showed the only statistically significant increase overall.
* Significant increases in visit rates among:

  * **65+ years old (2017 and 2018):** +28.7% and +29.3%
  * **Male patients (2018):** +19%
  * **Non-Hispanic White (2018):** +25.3%
  * **Children 0–17 (2020):** +39.2%
  * **Other Payment Providers (2018):** +80.5%

### 2. Condition-Specific Trends in Emergency Department Visits

#### 2.1 Trends in Specific Medical Conditions

##### A. Symptoms, signs, and abnormal clinical and laboratory findings

The analysis of emergency department visits for abnormal clinical and laboratory findings from 2016 to 2021 reveals significant trends across subgroups. Notably, the “Other” payment type category experienced the sharpest rate increase (+112% in 2018),and the non-Hispanic Other racial group showed consistent growth in both counts and rates across multiple years. 
During the COVID-19 pandemic, children (ages 0–17) saw a marked increase in ED visits, while senior citizens and males remained high-risk groups even before the pandemic. 
These findings highlight vulnerable populations and usage patterns that can inform targeted healthcare interventions.

| **Subgroup**              | **Year(s)** | **Trend Type**  | **Change (%)**          | **Notes**                    |
| ------------------------- | ----------- | --------------- | ----------------------- | ---------------------------- |
| Non-Hispanic Other (Race) | 2016        | Count Increase  | +68.83%                 | Continued in 2017            |
|                           | 2016        | Rate Increase   | +47.86%                 |                              |
|                           | 2017        | Count Increase  | +76.5%                  |                              |
|                           | 2017        | Rate Increase   | +59.51%                 |                              |
| Northeast Region          | 2017        | Count Increase  | +62.45%                 |                              |
|                           | 2018        | Count Increase  | +40.57%                 |                              |
|                           | 2017        | Rate Increase   | +60.57%                 |                              |
| “Other” Payment Type      | 2018        | Rate Surge      | +112.02%                | Highest overall increase     |
| Senior Citizens (65+)     | 2017        | Rate Increase   | +40.1%                  | Counts increased as well     |
| Male Patients             | 2016–2018   | Count Increases | 21.7% → 30.86% → 24.82% | Steady presence across years |
|                           | 2017        | Rate Increase   | +26.63%                 |                              |
| Children (0–17)           | 2020        | Count Increase  | +42.15%                 | During COVID-19 pandemic     |
|                           | 2020        | Rate Increase   | +42.8%                  |                              |
| Non-Hispanic Other (Race) | 2021        | Count Increase  | +48.86%                 | Post-pandemic continuation   |

---
##### B. Certain infectious and parasitic diseases
Emergency department visits for infectious and parasitic diseases showed steady increases before the pandemic, particularly among the non-Hispanic White population and adults aged 18–44. 
During the COVID-19 pandemic, sharp surges in infection-related visits were observed, especially in children (0–17 years) and regions like the South and West.
Increases were also notable among patients with private insurance, Medicaid recipients, and females, highlighting widespread impacts across demographic groups.
| **Subgroup**        | **Year(s)** | **Trend Type** | **Change (%)** | **Notes**                       |
| ------------------- | ----------- | -------------- | -------------- | ------------------------------- |
| Non-Hispanic White  | 2016        | Count Increase | +48.96%        | Continued growth in 2018        |
|                     | 2016        | Rate Increase  | +48.78%        |                                 |
|                     | 2018        | Count Increase | +73.63%        |                                 |
|                     | 2018        | Rate Increase  | +74.29%        |                                 |
| Age 18–44           | 2018        | Count Increase | +72.79%        | Significant pre-pandemic rise   |
| Children (0–17)     | 2020        | Count Increase | +106.29%       | Pandemic surge                  |
|                     | 2020        | Rate Increase  | +106.52%       |                                 |
| South Region        | 2020        | Count Increase | +97.84%        | Pandemic-related spike          |
|                     | 2020        | Rate Increase  | +94.87%        |                                 |
| Private Insurance   | 2020        | Count Increase | +76.75%        |                                 |
|                     | 2020        | Rate Increase  | +75.68%        |                                 |
| Medicaid Recipients | 2020        | Count Increase | +68.5%         |                                 |
| Female Patients     | 2020        | Count Increase | +48.41%        |                                 |
|                     | 2020        | Rate Increase  | +48.11%        |                                 |
| West Region         | 2021        | Rate Increase  | +83.56%        | Continued pandemic upward trend |

##### C. Diseases of the respiratory system
Before the COVID-19 pandemic, respiratory disease visits showed mixed patterns, with notable declines among Hispanic patients and Medicare recipients in 2019. 
During the pandemic (2020–2021), there was a pronounced resurgence in respiratory disease cases, especially among children (0–17 years), Medicaid recipients, and residents of the West region. 
The data highlights the significant and sustained impact of the pandemic on these groups.
| **Subgroup**        | **Year(s)** | **Trend Type** | **Change (%)** | **Notes**                        |
| ------------------- | ----------- | -------------- | -------------- | -------------------------------- |
| Hispanic Patients   | 2019        | Count Decrease | -39.44%        | Pre-pandemic significant decline |
|                     | 2019        | Rate Decrease  | -42.39%        |                                  |
| Medicare Recipients | 2019        | Rate Decrease  | -30.87%        |                                  |
| Children (0–17)     | 2020        | Count Increase | +96.47%        | Pandemic surge                   |
|                     | 2020        | Rate Increase  | +97.31%        |                                  |
|                     | 2021        | Rate Increase  | +57.00%        | Sustained impact                 |
| West Region         | 2021        | Count Increase | +68.46%        | Pandemic surge                   |
|                     | 2021        | Rate Increase  | +68.66%        |                                  |
| Medicaid Patients   | 2021        | Count Increase | +73.63%        |                                  |
|                     | 2021        | Rate Increase  | +62.14%        |                                  |
| Age 18–44           | 2021        | Count Increase | +45.13%        |                                  |
|                     | 2021        | Rate Increase  | +42.86%        |                                  |
| Non-Hispanic White  | 2021        | Count Increase | +39.51%        |                                  |
|                     | 2021        | Rate Increase  | +40.30%        |                                  |
| Male Patients       | 2021        | Count Increase | +38.84%        |                                  |
|                     | 2021        | Rate Increase  | +37.91%        |                                  |

**2.2-The Escalating Mental and Behavioral Health Crisis**
Data from 2016 to 2022 reveals a marked and sustained escalation in mental, behavioral, and neurodevelopmental disorders, with significant increases in both counts and rates across multiple demographic groups. 
Hispanic patients, males, Medicaid recipients, older adults, and residents of the Midwest show particularly sharp rises, underscoring an urgent need for targeted mental health interventions.
| **Subgroup**       | **Year(s)**            | **Measure** | **Trend Type** | **Change (%)**   | **Notes**         |
| ------------------ | ---------------------- | ----------- | -------------- | ---------------- | ----------------- |
| Hispanic Patients  | 2017                   | Count       | Increase       | +88.71%          | Primary diagnosis |
| Male Patients      | 2017                   | Count       | Increase       | +40.19%          | Primary diagnosis |
| Medicaid Patients  | 2017                   | Count       | Increase       | +42.61%          | Primary diagnosis |
| Children (0–17)    | 2018                   | Count       | Increase       | +76.23%          | Primary diagnosis |
| Adults (45–64)     | 2018                   | Count       | Increase       | +52.27%          | Primary diagnosis |
| Hispanic Patients  | 2017                   | Rate        | Increase       | +74.12%          | Primary diagnosis |
| Male Patients      | 2017                   | Rate        | Increase       | +35.53%          | Primary diagnosis |
| Children (0–17)    | 2018                   | Rate        | Increase       | +79.55%          | Primary diagnosis |
| Adults (45–64)     | 2018                   | Rate        | Increase       | +54.73%          | Primary diagnosis |
| Medicare Patients  | 2016–2019              | Count       | Increase       | 69.41%–111.31%   | Reason-for-visit  |
| Male Patients      | 2016                   | Count       | Increase       | +50.53%          | Reason-for-visit  |
| Adults (65+)       | 2016, 2017, 2018, 2021 | Count       | Increase       | 85.67%–107.06%   | Reason-for-visit  |
| Non-Hispanic Black | 2016, 2017, 2020       | Count       | Increase       | 67.65%–103.57%   | Reason-for-visit  |
| Midwest Region     | 2016, 2017             | Count       | Increase       | 142.94%, 104.47% | Reason-for-visit  |
| Midwest Region     | 2016                   | Rate        | Increase       | +138.78%         | Reason-for-visit  |
| Medicare Patients  | 2016–2020              | Rate        | Increase       | 58.06%–81.48%    | Reason-for-visit  |
| Adults (65+)       | 2017, 2018, 2021       | Rate        | Increase       | 66.95%–82.41%    | Reason-for-visit  |
| Non-Hispanic Black | 2017, 2020             | Rate        | Increase       | +94.62%          | Reason-for-visit  |
| Male Patients      | 2017, 2018             | Rate        | Increase       | 51.56%–53.97%    | Reason-for-visit  |
| Adults (45–65)     | 2017                   | Rate        | Increase       | +110.81%         | Reason-for-visit  |

**2.3.The Decline of Injury-Related Visits**
There was a significant decline in injury-related emergency department visits during 2016 and 2017, especially among younger patients (0–17 years) and uninsured populations. 
Both counts and rates decreased across several key demographics, indicating a meaningful reduction in injury and poisoning cases during this period.
| **Subgroup**       | **Year(s)** | **Measure** |  **Change (%)**| **Notes**                       |
| ------------------ | ----------- | ----------- | -------------- | ------------------------------- |
| Age 0–17           | 2016        | Count       | -30.66%        | Continued decline into 2017     |
|                    | 2017        | Count       | -29.87%        |                                 |
| Uninsured Patients | 2016        | Count       | -47.63%        | Largest decline among subgroups |
| Uninsured Patients | 2016        | Rate        | -47.75%        |                                 |
| Age 0–17           | 2016        | Rate        | -29.59%        | Continued decline into 2017     |
|                    | 2017        | Rate        | -28.79%        |                                 |
| Age 18–44          | 2016        | Rate        | -26.76%        |                                 |
| Non-Hispanic White | 2016        | Rate        | -24.15%        |                                 |
| Female Patients    | 2016        | Rate        | -20.11%        |                                 |
| Private Insurance  | 2016        | Rate        | -19.96%        |                                 |

**3.Key Symptom Trends in Emergency Department Visits**

The COVID-19 pandemic led to significant increases in emergency visits for acute symptoms like shortness of breath, cough, and vomiting, especially in children and certain demographic groups. Respiratory symptoms surged dramatically in 2020, reflecting COVID’s impact, while vomiting rose sharply among young and privately insured patients. 
These trends indicate both direct effects of the virus and indirect impacts such as delayed care and increased health-seeking behavior.
| **Subgroup**       | **Type**   | **Year(s)** | **Count–Rate Change (%)** | **Symptom**          |
| ------------------ | ---------- | ----------- | ------------------------- | -------------------- |
| Age 0–17           | Count–Rate | 2016        | 169.41 – 43.72            | Shortness of Breath  |
|                    | Count–Rate | 2017        | 120.97 – 125              | Shortness of Breath  |
|                    | Count–Rate | 2018        | 117.71 – 118.92           | Shortness of Breath  |
|                    | Count–Rate | 2020        | 198.82 – 200              | Cough                |
|                    | Count–Rate | 2020        | 92.43 – 93.88             | Vomiting             |
| South Region       | Count      | 2016        | 105.39                    | Shortness of Breath  |
| Northeast Region   | Count–Rate | 2018        | 187.16 – 181.82           | Shortness of Breath  |
|                    | Count      | 2017        | 135.14                    | Cough                |
|                    | Count      | 2016        | 72.43                     | Cough                |
| West Region        | Count–Rate | 2020        | 97.08 – 95.92             | Vomiting             |
|                    | Count      | 2021        | 136.25                    | Cough                |
| Male Patients      | Count      | 2016        | 81.31                     | Shortness of Breath  |
|                    | Count      | 2018        | 67.67                     | Shortness of Breath  |
|                    | Count–Rate | 2020        | 97.65 – 95.83             | Vomiting             |
| Non-Hispanic Black | Count–Rate | 2016        | 90.5 – 80.45              | Shortness of Breath  |
| Non-Hispanic White | Count      | 2020        | 63.21                     | Vomiting             |
| Private Insurance  | Count      | 2016        | 104.29                    | Shortness of Breath  |
|                    | Count–Rate | 2020        | 141.32 – 136.84           | Vomiting             |
|                    | Count–Rate | 2019–2020   | 55.32 – 55.32 *(near 60)* | Cough *(borderline)* |
| Medicaid Patients  | Count      | 2016        | 102.62                    | Shortness of Breath  |
| Medicare Patients  | Count      | 2016        | 79.9                      | Shortness of Breath  |

**4.A Deeper Look: Subgroup Narratives**

**Age-Based Trends:** Children (0–17) and older adults (65+) faced the largest increases in ED visits, especially for respiratory, gastrointestinal, and mental health issues. Notably, cough-related rates for children surged by 200% in 2020.

**Gender & Ethnicity:** Male patients showed significant rises in acute and mental health visits, with a 35.53% increase in mental health rates in 2017. Non-Hispanic Black and Hispanic groups also experienced notable spikes in specific conditions.

**Payer & Regional Differences:** Medicare and private insurance holders had substantial visit increases for pain, vomiting, and respiratory symptoms. The Northeast and West regions saw dramatic surges, such as a 181.82% rise in shortness of breath rates in the Northeast (2018).

These patterns reveal uneven impacts across populations, emphasizing the need for targeted, equitable public health strategies.


**5.No Significant change: A Closer Look at Potential Disparities**

Certain subgroups—such as female patients, Non-Hispanic Black, Hispanic, and other racial minorities—showed no statistically significant change in ED visits. This may indicate barriers to access, implicit bias, or cultural and economic factors influencing care-seeking or diagnosis, rather than truly stable healthcare utilization. 
These trends underscore the need for further investigation into structural inequities and healthcare disparities in emergency care.


**Conclusion:**

The analysis of Emergency Department (ED) visits from 2016 to 2022 reveals a complex and shifting landscape of healthcare utilization, with 2018 standing out as the only year with a statistically significant difference in overall visit counts compared to the 2022 baseline.
Beyond this single robust finding, the data highlights several consistent and impactful trends. The most prominent are the escalating crisis in **mental and behavioral health**, which showed large and sustained increases across many demographics, and a clear rise in acute symptom-related visits (e.g., respiratory, GI symptoms) during the pandemic years.
These surges were not uniform; they disproportionately affected key subgroups, including **children (0–17 years old), Senior citizens (65+ years old), male patients, and individuals with private insurance**, suggesting these populations were uniquely vulnerable to the health challenges of this period. Additionally, the data points to a notable decline in injury-related visits and an anomaly in different categories which is a positive indication. 
These findings underscore the critical need for targeted public health interventions tailored to these high-risk populations, particularly in addressing the ongoing mental health crisis and preparing for future public health events and spreading awareness regarding this matter.

**🔗 Links**

-📄 [PDF Report](P1002.pdf)
-📓 [Jupyter Notebook](P1002.ipynb)
-🗂️ [Images Archive (ZIP)](P1002VISUALS.zip)
-📊 [Dataset (CSVl File)](CLEANED_Estimates_of_Emergency_Department_Visits_in_the_United_States_from_2016-2022.csv)
-🌐 [Original Dataset Source] [CDC Health Data] (https://healthdata.gov/dataset/Estimates-of-Emergency-Department-Visits-in-the-Un/i3me-g36r/about_data)


