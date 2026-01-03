# FitPulse – Health Anomaly Detection  

## Milestone: Data Preprocessing

---

## Objective
Clean, preprocess, and integrate **Heart Rate, Steps, and Sleep** data into a unified dataset for health anomaly detection.  
The dataset is aligned at **minute-level granularity** for accurate time-series modeling.

---

## Dataset
- **Heart Rate (per second):** `heartrate_seconds_merged.csv`  
- **Steps (hourly):** `hourlySteps_merged.csv`  
- **Sleep (daily):** `sleepDay_merged.csv`  
Source: [Kaggle Fitbit Dataset](https://www.kaggle.com/datasets/raphfritzy/fitabase-data-4-12-16-5-12-16?resource=download)

---

## Tools
- Python, Google Colab  
- Pandas, NumPy  

---

## Preprocessing Steps

1. **Data Loading**  
   Loaded CSV files from Google Drive into Pandas DataFrames.

2. **Datetime Conversion**  
   Converted all timestamps to `datetime` objects with UTC timezone awareness.

3. **Heart Rate Aggregation**  
   Aggregated second-level heart rate data to **hourly averages**.

4. **Steps Aggregation**  
   Steps data was already hourly; merged with heart rate on `Id` and `Time`.

5. **Sleep Feature Engineering**  
   - Sleep data is daily; added `daily_sleep_date` for merge.  
   - Created features:  
     - `sleep_hours` (total minutes asleep ÷ 60)  
     - `sleep_efficiency` (TotalMinutesAsleep ÷ TotalTimeInBed)  
     - `fragmented_sleep` (binary: more than 1 sleep session)

6. **Missing Value Handling**  
   - Filled `sleep_hours` and `sleep_efficiency` with **per-user median**, fallback to **global median**.  
   - Steps missing → filled with `0`.  
   - Fragmented sleep → encoded as `0/1`.

7. **Column Cleanup**  
   Dropped intermediate columns like `SleepDay`, `TotalMinutesAsleep`, `TotalTimeInBed`, `TotalSleepRecords`, `date`.

8. **Final Dataset Features**
   | Column | Description |
   |--------|------------|
   | Id | User ID |
   | Time | Hour-level timestamp |
   | heart_rate | Avg heart rate per hour |
   | StepTotal | Total steps per hour |
   | sleep_efficiency | Sleep efficiency ratio |
   | fragmented_sleep | Binary: fragmented sleep (0/1) |
   | sleep_hours | Total sleep in hours |
   | daily_sleep_date | Date of sleep record |

- **No missing values**  
- **Shape:** 6,034 × 8

---

## Notes
- Sleep features are **constant across a day**, repeated for each hour; captured in `daily_sleep_date`.  
- This preprocessing is **Milestone-1 complete** and ready for modeling/anomaly detection in Milestone-2.

---

**Author:** Soumya Mishra  

