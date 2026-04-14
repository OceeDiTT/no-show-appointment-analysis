<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:134E5E,100:71B280&height=200&section=header&text=No-Show%20Appointment%20Analysis&fontSize=30&fontColor=ffffff&animation=fadeIn" />

### 🏥 No-Show Appointment Analysis  
### *Exploratory Data Analysis of Patient Appointment Attendance*

![Python](https://img.shields.io/badge/Language-Python-blue?style=for-the-badge)
![Analysis](https://img.shields.io/badge/Focus-EDA-green?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Data-Healthcare-orange?style=for-the-badge)

</div>

---

## Overview

This project explores patterns behind **patient no-shows in medical appointments** using Python-based exploratory data analysis (EDA).

The analysis aims to identify key factors influencing whether patients:
- ✅ Show up for appointments  
- ❌ Miss scheduled appointments  

---

## Objectives

- Analyze factors affecting appointment attendance  
- Investigate relationships between:
  - Waiting time  
  - Age  
  - Gender  
  - Alcohol consumption  
- Derive actionable insights to reduce no-show rates  

---

## Dataset Description

The dataset contains patient appointment records with features such as:

- `ScheduledDay` – Date appointment was scheduled  
- `AppointmentDay` – Actual appointment date  
- `Age` – Patient age  
- `Gender` – Male/Female  
- `Alcoholism` – Whether patient is alcoholic  
- `Neighbourhood` – Location of appointment  
- `No-show` – Target variable (Show / No-show)  

---

## Methodology

### 1. Data Cleaning & Preparation

- Converted date columns to datetime format  
- Created new feature:

```python
df_data['duration'] = df_data['appointmentday'].dt.date - df_data['scheduledday'].dt.date
df_data['duration'] = df_data['duration'].dt.days
```

This represents **waiting time between booking and appointment**  

---

### 2. Feature Engineering

- Created **waiting duration feature**  
- Converted **age into categorical groups** for better analysis.  

---

### 3. Exploratory Data Analysis

- Grouped data by `no_show`  
- Computed averages and distributions  
- Visualized relationships between variables  

Example:

```python
avg_day = df_data.groupby('no_show')['duration'].mean().round(2)
```

---

## Workflow

```text
Data Input 
   ↓
Data Wrangling
   ↓
Feature Engineering
   ↓
Exploratory Analysis
   ↓
Visualization
   ↓
Insight Generation
```

---

## Key Findings

### Waiting Time Matters
- Patients who **showed up**: ~8–9 days waiting time  
- Patients who **did not show**: ~15–16 days waiting time 

Conclusion: Longer waiting periods significantly increase no-show rates  

---

### Gender Influence
- Both male and female patients showed **similar commitment (~80% attendance)**

---

### Age Factor
- Age does **not strongly influence attendance overall**  
- However:
  - **Youths (18–37)** → highest no-show rate  
  - **Older adults (57+)** → most consistent attendance 

---

### Alcoholism
- Alcohol is **not a major factor** affecting attendance  
- ~80% of alcoholic patients still attended appointments

---

### Location Insight
- **Jardim Camburi** recorded the highest number of successful appointments

---

## Sample Results

<img src="" alt="">

---

## Tools & Libraries

- Python  
- Pandas  
- NumPy  
- Matplotlib  

---

## Reproducibility

1. Clone the repository  
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib
   ```
3. Open the Jupyter Notebook  
4. Run all cells sequentially  

---

## Future Recommendation

- [ ] Apply machine learning models (classification)  
- [ ] Perform feature importance ranking  
- [ ] Build predictive no-show model   

---

## References

- Kaggle Dataset  
- Stack Overflow (for implementation support)

---

<div align="center">

### ⭐ This project demonstrates practical EDA skills in healthcare analytics. Star if found useful

</div>
