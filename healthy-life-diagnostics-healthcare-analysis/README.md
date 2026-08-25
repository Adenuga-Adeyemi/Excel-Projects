# Healthcare Analytics Report – HealthyLife Diagnostics Clinic

![HealthyLife Diagnostics Clinic dashboard](./Images/healthy-life-diagnostics-dashboard.png)

## Introduction

In the ever-evolving field of healthcare, **data analytics** has emerged as a powerful tool, revolutionizing how patient care is delivered. With the vast amount of data generated within the healthcare ecosystem, leveraging data analytics techniques has become essential to uncover valuable insights and drive informed decision-making.

This report explores the role of data analytics in healthcare and its impact on transforming patient care. **HealthyLife Diagnostics Clinic** is a state-of-the-art medical facility providing high-quality diagnostic and treatment services. The clinic specializes in **preventative care**, **chronic disease management**, and **innovative treatments**, ensuring positive patient outcomes through data-driven decisions.

**Tool Used:** Microsoft Excel

---

## Problem Statement

The clinic needed a data analytics system to:

- Track patient demographics and their responsiveness to treatment  
- Assess treatment effectiveness across different modalities  
- Analyze doctor workload and patient satisfaction trends  

---

## Objectives

- **Analyze Patient Demographics:** Identify age and gender-based trends in patient visits and treatment responses  
- **Evaluate Treatment Effectiveness:** Measure success rates of different treatment methods  
- **Monitor Doctor Workload & Satisfaction:** Assess patient satisfaction based on specialty and workload  

---

## Dataset Overview

The dataset includes **5,000 rows and 14 columns**, categorized by:

- Gender  
- Age group  
- Medical conditions  
- Treatment modalities  
- Financial insights (e.g., treatment costs)  

> *Source: Mydataclique, 2025*

---

## Data Processing & Cleaning

### 1. Removing Duplicates

- Data was imported as a `.csv` into Excel.
- Duplicate records were checked based on `Patient ID`, `Age`, `Gender`, `Location`, `Visit Type`, and `Medical Conditions`.  
- **Result:** No duplicates found.

> *Source: Analyst Idea, 2025*

---

### 2. Standardizing Data Formats

- **Text to Number Conversion:** Treatment cost, insurance coverage  
- **Number to Text Conversion:** Gender, medical condition  
- **Date Formatting:** All dates formatted to `YYYY-MM-DD` using PowerQuery  

> *Source: Analyst Idea, 2025*

---

### 3. Import into Power Pivot

Clean data was imported into **Power Pivot**. Custom **DAX formulas** were created to compute key metrics.

---

## DAX Formulas for Key Metrics

-- 1. Total Male Patients
<```DAX>
Total Male Patients = CALCULATE(COUNT(HealthData[Patient ID]), HealthData[Gender] = "Male")
</DAX>

-- 2. Total Female Patients
<```DAX>
Total Female Patients = CALCULATE(COUNT(HealthData[Patient ID]), HealthData[Gender] = "Female")
</DAX>

-- 3. Total Other Patients
<```DAX>
Total Other Patients = CALCULATE(COUNT(HealthData[Patient ID]), HealthData[Gender] = "Other")
</DAX>

-- 4. Gender Ratios
<```DAX>
Ratio Female vs Others = DIVIDE(COUNTROWS(FILTER(HealthData, HealthData[Gender] = "Female")), COUNTROWS(FILTER(HealthData, HealthData[Gender] <> "Female")), 0)
Ratio Male vs Others = DIVIDE(COUNTROWS(FILTER(HealthData, HealthData[Gender] = "Male")), COUNTROWS(FILTER(HealthData, HealthData[Gender] <> "Male")), 0)
</DAX>

-- 5. Treatment Success Rate
<```DAX>
Treatment Success Rate = DIVIDE(COUNTROWS(FILTER(HealthData, HealthData[Outcome] = "Improved")), COUNTROWS(HealthData), 0)
</DAX>

-- 6. Follow-up Compliance Rate
<```DAX>
Follow Up Compliance Rate = DIVIDE(COUNTROWS(FILTER(HealthData, HealthData[Follow-up Required] = "Yes")), COUNTROWS(HealthData), 0)
</DAX>

-- 7. Average Treatment Duration
<```DAX>
Average Treatment Duration = SUM(HealthData[Treatment Duration (Days)]) / COUNT(HealthData[Patient ID])
</DAX>

-- 8. Financial Metrics
<```DAX>
Avg Treatment Cost = AVERAGE(HealthData[Treatment Cost])
Avg Insurance Coverage = AVERAGE(HealthData[Insurance Coverage (%)])
</DAX>

---

# Analysis & Insights

## KPIs Dashboard Overview

- **Male Patients:** 1,660 (33.2%)  
- **Female Patients:** 1,681 (33.6%)  
- **Other Patients:** 1,659 (33.2%)  
- **Total Patients:** 5,000  

### Treatment Metrics

- **Avg Treatment Duration:** 45 days  
- **Follow-Up Compliance Rate:** 48.98%  
- **Treatment Success Rate:** 33.02%  
- **Avg Insurance Coverage:** 5.0%  
- **Avg Patient Satisfaction Score:** 3.0 / 5  
- **Total Treatment Cost:** $12,830,204.65  

### Doctor's Workload

- **Total Active Doctors:** 1,000  
- **Female-to-Others Ratio:** 50.65%  
- **Male-to-Others Ratio:** 49.70%  

---

## Deep Dive Analysis

### 1. Patient Demographics

- **Largest Age Group:** 66+ years (1,744 patients)  
- **Smallest Age Group:** 36–50 years (771 patients)  
- **Most Responsive:** Under 18 and 19–35 years  

**Recommendations:**
- Introduce chronic disease management for older patients  
- Expand preventative care for younger groups  

---

### 2. Treatment Effectiveness

- **Top Conditions:**  
  - Anxiety (584)  
  - Flu (577)  
  - Back Pain (557)  
- **Older Patients:** More Arthritis & Back Pain  
- **Young Patients:** More Anxiety & Flu  
- **Top Treatment:** Medication & Lifestyle Therapy (48.98%)  
- **Effective for Youth:** Physical Therapy  
- **High Success Ages:** 36–50 (Surgical Interventions)  

**Recommendations:**
- Post-surgical rehabilitation for 36–50 age group  
- Combine medication + lifestyle therapy  
- Improve insurance policies to reduce out-of-pocket costs  

---

### 3. Doctor Specialty & Satisfaction

- **Highest Workload:** General Practitioners & Orthopedic Specialists  
- **Highest Satisfaction:** Endocrinologists & Physical Therapists  
- **Low Compliance Rate:** 48.98%  

**Recommendations:**
- Redistribute patient load to reduce burnout  
- Engage age 36–50 group to improve satisfaction  
- Implement AI-assisted diagnostics for busy specialties  
- Promote mental health consultations  

---

## Conclusion

The **HealthyLife Diagnostics Clinic Healthcare Dashboard** provides deep insights into patient demographics, treatment performance, and doctor workload.  
**Future steps** include using **predictive analytics** for patient risk modeling and **personalized engagement** to enhance care.

---

🔗 **Follow me on LinkedIn:** [Pearl Adeyemi](https://www.linkedin.com/in/pearladeyemi/)

