# Milestone 3: Anomaly Detection and Visualization

## Objective of Milestone 3
The objective of this milestone is to analyze wearable sensor time-series data to:

- Model expected temporal trends in physiological signals using Facebook Prophet
- Identify anomalous patterns in heart rate and sleep efficiency
- Apply rule-based, residual-based, and cluster-based anomaly detection techniques
- Visualize anomalous events across multiple users
- Prepare insights and visual outputs for reporting and further analysis

---

## Dataset Description
The dataset consists of minute-level wearable sensor data collected from multiple users.  
Each record contains the following attributes:

- `Id` – Unique participant identifier  
- `Time` – Timestamp of measurement  
- `heart_rate` – Heart rate value  
- `sleep_efficiency` – Sleep quality indicator (0–1)
The dataset was pre-cleaned to remove invalid values before analysis.

---

## Steps Performed

### 1. Heart Rate Trend Modeling
- Heart rate data was aggregated to hourly mean values per user.
-Facebook Prophet was applied to model:
   - Daily trends
   - Weekly seasonality
- Forecasts were generated along with upper and lower confidence intervals.
  
---

### 2. Heart Rate Anomaly Detection (Model-Based)
- Anomalies were identified when observed heart rate values fell outside Prophet’s confidence intervals.
- Residual-based detection helped capture:
   - Sudden spikes
   - Abrupt drops
- Detected anomalies were labeled for further analysis and visualization.
---

### 3. Sleep Pattern Anomaly Detection (Rule-Based)
- Domain-specific thresholds were defined for sleep efficiency:
   - Normal range: 0.9 – 1.0
- Records outside this range were flagged as sleep anomalies.
- Threshold-based detection enabled simple and interpretable anomaly identification.
---
### 4. Cluster-Based Anomaly Identification
- Behavioral features extracted in Milestone 2 were reused.
- KMeans clustering was applied to identify typical behavioral patterns.
- Data points with unusually large distances from cluster centroids were flagged as cluster-based anomalies.
- This approach captured abnormal behavior not detected by simple thresholds.

---
### 5. Anomaly Labeling

- Anomaly indicators from:
   - Prophet residuals
   - Rule-based thresholds
   - Cluster-based outliers
- Were combined to create a final unified anomaly label.
- Each data point was clearly categorized as:
   - Normal behavior
   - Anomalous behavior

---
### 6.Visualization and Reporting
- Anomalies were visualized using Matplotlib (Plotly was not used).
- Generated visual outputs include:
   - `heart_rate_anomalies.png`
   - `sleep_anomalies.png`
   - `rule_based.png`
   - `hr_prophet.png`
- Time-series plots highlight anomalous points using markers and overlays.
- Visualizations provide a clear and intuitive understanding of abnormal behavior patterns.

---
## Tools and Libraries Used
- **Python**
- **Pandas, NumPy**
- **Facebook Prophet**
- **Matplotlib**
- **Scikit-learn**
- **TSFresh**
- **Google Colab**

---

## Key Observations
- Heart rate anomalies reveal sudden spikes or drops beyond expected physiological trends.
- Sleep efficiency anomalies highlight periods of unusually poor or irregular sleep.
- Cluster-based detection captures subtle behavioral outliers missed by simple thresholds.
- Combining multiple detection strategies improves robustness and reliability.
- Visual analysis enables rapid identification of abnormal health patterns.
---

## Author
Soumya Mishra
