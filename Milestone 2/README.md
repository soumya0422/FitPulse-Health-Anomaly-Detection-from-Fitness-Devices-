# Milestone 2: Trend Modeling and Behavioral Pattern Analysis

## Objective of Milestone 2
The objective of this milestone is to analyze wearable sensor time-series data to:
- Extract meaningful time-series features using automated feature extraction
- Model behavioral patterns using unsupervised learning techniques
- Identify latent behavioral groups and abnormal activity patterns
- Reduce high-dimensional feature space for visualization and interpretation

---

## Dataset Description
The dataset consists of wearable sensor data collected from multiple users.Each record contains the following attributes:
- `Id` – Unique participant identifier  
- `Time` – Timestamp of measurement  
- `heart_rate` – Heart rate value  
- `StepTotal` – Total steps
- `sleep_efficiency` – Sleep quality indicator
- `sleep_hours` – Total sleep duration

The dataset was cleaned to remove missing, infinite, and extreme values prior to analysis.

---

## Steps Performed
### 1. Data Cleaning and Validation

- Checked for missing, infinite, and overflow values
- Replaced infinite values with NaN
- Filled missing numeric values using column-wise mean
- Ensured time-series consistency by sorting by Id and Time

### 2. Time-Series Feature Extraction

- Converted data into long-format suitable for TSFresh
- Extracted features for:
   - Heart rate
   - Step total
   - Sleep hours
- Applied Minimal and Comprehensive TSFresh feature sets
- Removed unstable features with excessive missing values
- Applied Variance Thresholding to remove low-variance features

### 3. Behavioral Pattern Clustering

- Standardized extracted features using StandardScaler
- Applied clustering techniques:
   - KMeans
   - DBSCAN
- Identified behavioral clusters representing different activity patterns
- Reduced dimensionality for visualization using:
   - PCA
   - t-SNE
   - UMAP


## Tools and Libraries Used
- **Python**
- **Pandas, NumPy**
- **Facebook Prophet**
- **TSFresh**
- **Scikit-learn**
- **Matplotlib**
- **Google Colab**

---

## Key Observations
- TSFresh successfully captured rich statistical and frequency-based patterns
- Clustering revealed distinct behavioral groups
- Dimensionality reduction showed clear separation between clusters
- Some clusters exhibited high variability, indicating atypical behavior patterns

---

## Author
Soumya Mishra

