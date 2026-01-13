# FitPulse – Health Anomaly Dashboard Report

## Objective
The FitPulse project aims to provide a **real-time health monitoring dashboard** for users by processing fitness data (heart rate, steps, sleep), performing anomaly detection, and generating actionable health insights. The dashboard helps track daily metrics, identify abnormal patterns, and generate risk reports for proactive health management.

---

## Dashboard Workflow

1. **Data Upload & Preprocessing (Module 1)**
   - Users upload CSV or JSON fitness data containing `Id`, `date`, `avg_heart_rate`, `daily_steps`, and `hours_sleep`.
   - Backend cleans the data:
     - Converts dates to datetime objects.
     - Fills missing heart rate and sleep values with median; steps with 0.
     - Resamples data daily per user.
   - Outputs a clean dataset (`clean_data.csv`).

2. **Feature Extraction & Modeling (Module 2)**
   - Calculates 7-day rolling averages and standard deviations of heart rate.
   - Scales numeric features and applies **DBSCAN clustering** to detect outliers.
   - Forecasts average heart rate over time using **Prophet**.
   - Outputs feature-enriched data (`feature_data.csv`) and anomaly clusters.

3. **Anomaly Detection (Module 3)**
   - Flags health anomalies:
     - Heart rate >120 or <40
     - Sleep <4 or >12 hours
     - Cluster outliers detected by DBSCAN
   - Generates alerts with severity labels (`High`, `Medium`, `Low`) based on frequency.
   - Outputs anomaly report (`module3_alerts.csv`).

4. **Dashboard Data (Visualization)**
   - Heart rate and steps trends visualized using **Plotly charts**.
   - Summary metrics displayed for quick overview:
     - Average heart rate
     - Average steps
     - Total records loaded

5. **Insights & Reports (Module 4)**
   - Generates **user-specific insights** based on anomalies and severity.
   - Allows download of clean dataset and anomaly reports.
   - Supports proactive health risk analysis.

---

## Tools & Libraries Used
| Purpose | Library / Tool |
|---------|----------------|
| Web API | FastAPI |
| Dashboard | Streamlit |
| Visualization | Plotly Express |
| Forecasting | Prophet |
| Clustering & Anomaly Detection | scikit-learn (DBSCAN, StandardScaler) |
| Data Handling | pandas, numpy |
| Automation / Deployment | pyngrok, threading |
| Others | requests, datetime, matplotlib |

---

## Key Insights from the Dashboard
- **User-Level Trends**
  - Average heart rate and step count tracked over time.
  - Detection of unusual deviations from normal patterns.
- **Anomaly Detection**
  - High-risk users flagged for sustained abnormal heart rates or sleep patterns.
  - Cluster-based outlier detection highlights hidden anomalies.
- **Actionable Insights**
  - Users with repeated alerts are identified with severity levels (Low, Medium, High).
  - Reports allow for offline review and proactive health intervention.
- **Forecasting**
  - 30-day heart rate trend predictions help anticipate potential anomalies.

---

## Screenshot References
1. **Overview Tab** – Dataset preview, user metrics, daily summaries.  
   `![Screenshot](screenshots/overview.png)`  
2. **Health Dashboard** – Heart rate trends and steps over time.  
   `![Screenshot](screenshots/health_dashboard.png)`  
3. **Anomaly Detection** – Bar chart of detected anomalies and severity.  
   `![Screenshot](screenshots/anomaly_detection.png)`  
4. **Insights & Reports** – Generated risk insights per user and download options.  
   `![Screenshot](screenshots/insights_reports.png)`

---
