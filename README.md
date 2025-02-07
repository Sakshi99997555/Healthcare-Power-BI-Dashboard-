# Healthcare-Power-BI-Dashboard-

Biased Leukemia Cancer Dashboard - README

📌 Project Overview

This project involves the development of an interactive, multi-page Power BI dashboard to analyze a biased leukemia dataset and extract meaningful insights. The dashboard helps in understanding key trends, patient demographics, treatment effectiveness, and survival rates.

🎯 Objectives

Develop a user-friendly, interactive dashboard.

Identify age, gender, and regional biases in leukemia data.

Provide data-driven insights for healthcare professionals.

Enhance decision-making using DAX-powered calculations.

📊 Dashboard Structure

1️⃣ Home Page

✔️ Intuitive landing page for easy navigation.✔️ Key KPIs: Total Patients, Leukemia Cases, Survival Rate.✔️ Navigation Buttons for quick access to insights.✔️ Background Design & User Experience Enhancements.

2️⃣ Patient Demographics Page

📌 Visuals:

Age Distribution (Histogram).

Gender Ratio (Pie Chart).

Geographical Distribution (Map).

Leukemia Cases by Age Group (Stacked Column Chart).

Survival Rate by Gender (Bar Chart).

Slicers: Age, Gender, Region.

📌 Key Insights:

Higher leukemia cases in older age groups.

Gender-based disparities in diagnosis rates.

Certain regions show higher leukemia prevalence.

3️⃣ Clinical Findings & Treatment Page

📌 Visuals:

Diagnosis vs. Treatment Timeline (Line Chart).

Survival Rate by Treatment Type (Bar Chart).

Treatment Effectiveness by Age Group (Stacked Column Chart).

Recovery Rate by Gender (Donut Chart).

Slicers: Treatment Type, Age, Gender.

📌 Key Insights:

Early diagnosis significantly improves survival.

Some treatments work better for specific age groups.

Gender-based variations in recovery rates.

📂 Data Processing & Cleaning Steps

✅ Data Import:

Imported CSV file into Power BI using Power Query.

Applied necessary data transformations.

✅ Data Preprocessing & Cleaning:

Removed duplicate and missing values.

Created custom columns for age groups.

Standardized categorical values (e.g., "Male" vs "M").

Used DAX formulas to create calculated measures.

📌 DAX Formulas Used

✅ Total Patients:

Total Patients = COUNT( 'Leukemia'[Patient_ID] )

✅ Leukemia Cases:

Leukemia Cases = CALCULATE( COUNT( 'Leukemia'[Patient_ID] ), 'Leukemia'[Leukemia_Status] = "Positive" )

✅ Survival Rate:

Survival Rate =
DIVIDE( COUNTROWS( FILTER( 'Leukemia', 'Leukemia'[Leukemia_Status] = "Negative" ) ),
        COUNTROWS( 'Leukemia' ),
        0 )

✅ Age Group Classification:

Age Group =
SWITCH( TRUE(),
    'Leukemia'[Age] <= 20, "0-20",
    'Leukemia'[Age] <= 40, "21-40",
    'Leukemia'[Age] <= 60, "41-60",
    "60+"
)

✅ Treatment Effectiveness Measure:

Treatment Success Rate =
DIVIDE( COUNTROWS( FILTER( 'Leukemia', 'Leukemia'[Treatment_Result] = "Successful" ) ),
        COUNTROWS( 'Leukemia' ),
        0 )

📢 Key Takeaways

📍 Early diagnosis leads to higher survival rates.📍 Treatment effectiveness varies by age and gender.📍 Certain regions have higher leukemia incidence rates, indicating possible environmental/genetic factors.📍 Data biases exist in treatment allocation and diagnosis.

🚀 Conclusion

This Power BI dashboard provides data-driven insights into leukemia trends and can help healthcare professionals make informed decisions. It highlights critical biases in treatment and diagnosis, enabling better patient care strategies.

💡 Future Scope: Predictive modeling for early leukemia detection using AI/ML integration.
