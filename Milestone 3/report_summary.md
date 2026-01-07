# Milestone 3: Anomaly Detection and Visualization

## Objective of Milestone 3
The objective of this milestone is to analyze wearable sensor time-series data to:
- Model expected trends in heart rate and sleep efficiency using Facebook Prophet
- Identify anomalies in heart rate and sleep efficiency
- Visualize anomalous events across multiple users
- Prepare visualizations and insights for reporting and further analysis

---

## Dataset Description
The dataset consists of minute-level wearable sensor data collected from multiple users.  
Each record contains the following attributes:

- `Id` – Unique participant identifier  
- `Time` – Timestamp of measurement  
- `heart_rate` – Heart rate value  
- `sleep_efficiency' – Sleep quality indicator (0–1)
The dataset was pre-cleaned to remove invalid values before analysis.

---

## Steps Performed

### 1. Heart Rate Trend Modeling
- Aggregated heart rate data by hourly mean per user.
- Applied Facebook Prophet to model daily and weekly temporal trends.
- Forecasted expected heart rate values along with confidence intervals.
- Calculated residuals (observed – predicted values) for anomaly detection.

---

### 2. Heart Rate Anomaly Detection
- Flagged anomalies where observed heart rate fell outside Prophet’s predicted confidence intervals.
- Counted the number of anomalous heart rate events.
- Visualized anomalies by overlaying actual heart rate values with expected trends and confidence intervals.
---

### 3. Sleep Pattern Anomaly Detection
- Defined thresholds for sleep efficiency (0.9 – 1.0).
- Flagged records outside this range as sleep anomalies.
- Visualized sleep efficiency over time across all users to identify unusual patterns.

### 4. Visualization and Reporting

- Anomalies were visualized using Matplotlib.
- Generated plots for reporting and further analysis:
    - heart_rate_anomalies.png
    - sleep_anomalies.png
- Visualizations help in identifying unusual behavior patterns quickly.

---

## Tools and Libraries Used
- **Python**
- **Pandas, NumPy**
- **Facebook Prophet**
- **Matplotlib**
- **Google Colab**

---

## Key Observations
- Heart rate anomalies indicate sudden spikes or drops outside normal trends.
- Sleep anomalies highlight periods of unusually low or high sleep efficiency.
- Visualizations provide a clear overview of anomalous behavior across users.
- Residual- and threshold-based detection effectively identify abnormal events.

---

## Author
Soumya Mishra
