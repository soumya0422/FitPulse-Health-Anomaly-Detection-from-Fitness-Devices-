# FitPulse – Health Anomaly Detection  
## Milestone: Data Preprocessing

---

## Objective
Clean, preprocess, and integrate Heart Rate, Steps, and Sleep data into a **minute-level aligned dataset** for health anomaly analysis.

---

## Dataset
- Heart Rate (per second): `heartrate_seconds_merged.csv`  
- Steps (hourly): `hourlySteps_merged.csv`  
- Sleep (daily): `sleepDay_merged.csv`  
Source: [Kaggle Fitbit Dataset]([https://www.kaggle.com/datasets/arashnic/fitbit](https://www.kaggle.com/datasets/raphfritzy/fitabase-data-4-12-16-5-12-16?resource=download ))

---

## Tools
- Python, Google Colab  
- Pandas, NumPy  
- (Optional: Matplotlib, Seaborn)

---

## Steps Performed
1. Loaded CSVs from Google Drive.  
2. Converted timestamps to datetime (UTC).  
3. Aggregated heart rate to **1-minute** averages.  
4. Calculated **steps per minute** and normalized **sleep per minute**.  
5. Merged datasets on `Id` and time (`Date`/`Hour`).  
6. Filled missing values with `0`.  
7. Dropped intermediate columns, sorted, and created final cleaned dataset.

---

## Final Dataset
| Column | Description |
|--------|------------|
| Id | User ID |
| Time | Minute-level timestamp |
| heart_rate | Avg heart rate per minute |
| Steps_per_minute | Steps per minute |
| Sleep_per_minute | Normalized sleep fraction |

- Shape: **334,630 × 5**  
- No missing values; ready for ML analysis

---

**Author:** Soumya Mishra
