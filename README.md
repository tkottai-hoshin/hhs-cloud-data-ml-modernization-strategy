  Overview:

This repository documents the strategic approach and technical thinking behind a large-scale cloud modernization effort supporting public health organizations within the U.S. Department of Health and Human Services (HHS) ecosystem, with a focus on enabling modern data and machine learning capabilities for scientists, analysts, and public health researchers.

The work involved application portfolio assessment, cloud architecture strategy (AWS and Azure), and the design of a modern data platform approach using Databricks to support advanced analytics and machine learning use cases.

A concrete technical example is included: an end-to-end machine learning project using publicly available NHANES data to predict Type 2 Diabetes risk. This example illustrates the type of data science work that becomes practical once legacy public health data and applications are modernized and made available on a governed, scalable platform.


1. Context

I led one of four discovery pods on a major cloud modernization engagement. My pod consisted of six team members and focused on conducting technical and business discovery sessions with:

- Public health scientists
- Department heads
- Data analytics and epidemiology teams
- Application & System owners

The broader effort involved assessing a large portfolio of applications (800+) to determine cloud readiness and modernization pathways.

2. Problem

The COVID-19 pandemic exposed significant limitations in public health data infrastructure — fragmented systems, delayed data sharing, and limited ability to perform advanced analytics at scale. 

In response, the Centers for Disease Control and Prevention (CDC) accelerated its **Data Modernization Initiative (DMI)** and related cloud modernization efforts. A key public contract in this space was the multi-year cloud modernization award to Accenture Federal Services to help migrate and modernize CDC systems into secure cloud environments.
https://www.cdc.gov/public-health-data-strategy/php/index.html

The core challenge was not simply moving applications to the cloud, but creating an environment where public health data could be:

- Securely integrated
- Easily discoverable
- Available for modern analytics and machine learning by researchers and scientists

3. Approach & Framework

Application Rationalization – The 7Rs Framework

Every application was evaluated using the industry-standard **7Rs** migration strategies:

- Retire – Decommission redundant or obsolete systems
- Retain – Keep certain systems on-premises when migration was not justified
- Rehost – Lift-and-shift to cloud infrastructure
- Replatform – Move with minor optimizations (e.g., managed databases)
- Replace / Repurchase – Move to modern SaaS solutions
- Refactor / Rearchitect – Rebuild for cloud-native capabilities
- Reimagine – Redesign processes to fully leverage cloud and data platforms

### Target Architecture

- Cloud Platforms: AWS and Azure (hybrid/multi-cloud strategy)
- Data Platform: Databricks (Lakehouse architecture) as the foundation for analytics and machine learning
- Goal: Enable governed, scalable data access so that scientists and analysts could perform modern data science without depending on fragmented legacy systems


4. Technical Demonstration: NHANES Diabetes Risk Prediction

To illustrate the type of machine learning work that a modernized data platform enables, this repository includes a complete end-to-end ML project using publicly available **NHANES** (National Health and Nutrition Examination Survey) data.

Project Summary
- Objective: Predict Type 2 Diabetes risk in adults
- Data Sources: NHANES Demographics, Laboratory (HbA1c), and Examination (Body Measures) files
- Key Steps:
  - Data ingestion, cleaning, and merging - Data from https://www.cdc.gov/nchs/nhanes/index.html
           'P_BMX.xpt',
           'P_GLU.xpt',
           'P_DEMO.xpt',
           'P_INS.xpt',
           'P_GHB.xpt',
           'P_BPXO.xpt',
           'P_TCHOL.xpt'
    
  - Feature engineering
  - Handling class imbalance
  - Model training (Logistic Regression, Random Forest, XGBoost)
  - Model evaluation and feature importance analysis
  - How to use past data to forecast future data
  - Demo / POC for Department of Public Health, actual data from National Health AND Nutrition Examination Survey (NHANES)

- Key Insight: Age and waist circumference were the strongest predictors of diabetes risk in the dataset

This example demonstrates the full workflow that public health data scientists would be able to run more easily once data is centralized, governed, and accessible on a platform such as Databricks.

→ See the notebook: NHANES_diabetes_prediction.ipynb

5. Key Takeaways

- Cloud modernization in public health is most valuable when it goes beyond infrastructure and enables **data + AI/ML** use cases.
- Structured discovery with scientists and analysts is critical to understanding real analytical needs.
- A modern lakehouse platform (Databricks) combined with strong cloud foundations (AWS/Azure) creates the conditions for scalable, governed machine learning.
- Even relatively simple, well-executed ML projects on public health data can surface actionable insights (as shown in the NHANES example).

---

Technologies & Tools Referenced

- Cloud: AWS, Azure
- Data Platform: Databricks
- Migration Framework: 7Rs
- ML Example: Python, pandas, scikit-learn, XGBoost, Plotly
- Data Source: NHANES (CDC)

