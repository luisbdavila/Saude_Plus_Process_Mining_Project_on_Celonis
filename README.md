# Saude_Plus_Process_Mining_Project_on_Celonis
## Project Overview
This repository contains the process mining analysis of Saúde+, a mid-sized private medical clinic specializing in orthopedics, general medicine, and physiotherapy. The project was developed using Celonis to address management concerns regarding declining service efficiency and potential inequalities in patient care.
The analysis focuses on the end-to-end patient journey for medical appointments, identifying bottlenecks, process deviations, and disparities based on patient profiles.

## Data Architecture & ETL
The analysis is based on two primary datasets processed through an ETL (Extract, Transform, Load) pipeline in Celonis:
+ Case Table: Contains demographic and clinical attributes for 1,190 unique cases, including age, gender, region, insurance status, chronic conditions, and satisfaction scores.
+ Event Log: Records 5,055 activities across 15 unique activity types, including timestamps for each step in the patient journey.
+ Data Model: The tables were joined using a 1:N relationship on the CASE_ID field, linking patient demographics to their specific sequence of clinical activities.


## Key Insights
**1. Process Deviations & Efficiency**
+ The "Happy Path": Surprisingly, the most common variant (23% of cases) is an undesired one where patients check in and are immediately told to return another day.
+ Conformance: Only 38% of cases follow the intended process model.
+ Bottlenecks: Non-conforming cases often involve "Waiting for Doctor" (6% of cases), which adds an average of 11 minutes to the throughput time.

**2. Patient Profile Analysis**
+ Insurance Inequality: Insured patients report significantly higher satisfaction (4.1) compared to uninsured patients (3.22). Uninsured patients are told to return another day 40% of the time.
+ Age Gaps: Patients under 40 have an average satisfaction of 4.17, while those over 40 drop to 3.38. Older patients (55+) are more likely to experience the "return another day" variant.
+ Regional Issues: Patients from the Islands experience the highest frequency of system errors, while those from the South report the lowest satisfaction levels (3.39).
+ Gender: Analysis confirmed that gender does not significantly impact the level of care or satisfaction scores.

**3. Action Flows**
To proactively manage data quality, a Celonis Action Flow was created to automatically email a CSV report to administrators whenever a "System Error" or "Incomplete Information" activity is detected.

## Recommendations
+ Process Optimization: Investigate why 23% of patients are sent home at check-in to reduce the "Return Another Day" rate.
+ Digital Accessibility: Simplify the digital interface for patients over 60 to reduce "Incomplete Information" errors.
+ Equal Care Initiatives: Standardize procedures for uninsured patients to bridge the satisfaction gap with insured clients.
+ Technical Audit: Review data integration for the Islands region to resolve recurring system errors.
