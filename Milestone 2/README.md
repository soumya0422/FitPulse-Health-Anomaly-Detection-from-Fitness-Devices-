# Milestone 2: Trend Modeling and Behavioral Pattern Analysis

## Objective of Milestone 2
The objective of this milestone is to analyze wearable sensor time-series data to:
- Model temporal trends and seasonal patterns using Facebook Prophet
- Detect unusual behavior by analyzing deviations from expected trends
- Extract meaningful time-series features
- Group users or time windows into behavioral clusters using unsupervised learning techniques

---

## Dataset Description
The dataset consists of minute-level wearable sensor data collected from multiple users.  
Each record contains the following attributes:

- `Id` – Unique participant identifier  
- `Time` – Timestamp of measurement  
- `heart_rate` – Heart rate value  
- `Steps_per_minute` – Step count per minute  
- `Sleep_per_minute` – Sleep indicator per minute  

The dataset was pre-cleaned to remove invalid values before analysis.

---

## Steps Performed

### 1. Feature Extraction
- Time-series features were automatically extracted using **TSFresh**.
- Features include statistical and frequency-domain characteristics such as:
  - Mean, variance, entropy
  - Energy and change-based metrics
- Features were extracted for heart rate, steps, and sleep signals.
- Daily time windows were used to represent behavioral patterns.

---

### 2. Trend Modeling and Anomaly Detection
- **Facebook Prophet** was applied to model temporal trends and seasonality.
- Forecasts were generated along with confidence intervals.
- Deviations from forecasted bounds were used to identify anomalous behavior.
- Trend modeling and anomaly detection were performed for:
  - Heart rate
  - Steps per minute
  - Sleep per minute
- Anomalies were visualized by overlaying actual values with forecast confidence intervals.

---

### 3. Behavioral Pattern Clustering
- Extracted TSFresh features were standardized and clustered using **KMeans**.
- The optimal number of clusters was evaluated using **Silhouette Score**.
- Clusters represent different behavioral patterns, including:
  - Normal activity patterns
  - Atypical or unusual behavior days
- Cluster-wise feature averages were analyzed to interpret behavioral differences.

---

## Tools and Libraries Used
- **Python**
- **Pandas, NumPy**
- **Facebook Prophet**
- **TSFresh**
- **Scikit-learn**
- **Matplotlib, Plotly**
- **Google Colab**

---

## Key Observations
- Clear temporal trends were observed in heart rate, step count, and sleep patterns.
- Prophet-based forecasting effectively identified deviations representing potential anomalies.
- Clustering revealed distinct behavioral groups corresponding to different activity levels.
- Certain clusters exhibited higher variability and entropy, indicating atypical behavior.


---

## Author
Soumya Mishra

