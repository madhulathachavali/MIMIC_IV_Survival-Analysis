# 🏥 Sepsis Onset in Emergency Department

This analysis uses the **MIMIC-IV-ED** dataset to identify key factors influencing sepsis onset in emergency department (ED) patients. The goal is to provide **actionable insights** to improve patient care and hospital operations.

---

## 🔍 Key Insights
- 👩 **Females** are at a higher risk for developing sepsis compared to males.  
- 👨‍⚕️ **White patients** represent the highest number of sepsis cases, followed by **Black/African American** and **Hispanic/Latino** patients.  
- 💓 **Vital signs**, especially **heart rate** and **oxygen saturation**, are strong predictors of sepsis risk.

---

## 📊 Key Findings

### 1️⃣ Demographics
- 👩‍⚕️ Females: 16,272 cases  
- 👨‍⚕️ Males: 10,140 cases  
- ⚪ White patients: 15,826 cases  
- ⚫ Black/African American: 4,271 cases  
- 🇵🇷 Puerto Rican: 1,589 cases

<img width="797" alt="image" src="https://github.com/user-attachments/assets/47466f48-7bb2-4b15-90f7-521ca373276f" />

---

### 2️⃣ Vital Signs Impact
- The first few hours are critical for patient monitoring as both heart rate and oxygen saturation exhibit a sharp decline in survival probability over time, dropping from 1 to a crucial 0.6 within the first 10 hours, and continuing to decrease to 0.3 at 20 hours
  
<img width="803" alt="image" src="https://github.com/user-attachments/assets/b55e8eb9-ca43-4837-a842-53e04cacec97" />


---

### 3️⃣ Clinical Factors
- 🚑 **Mode of arrival** and 🏥 **triage acuity** significantly influence sepsis risk.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/17201695-8568-4af9-bd97-a5e0b6068048" />

---

## 📈 Survival Analysis Insights

### 📊 **Cox Proportional Hazards Model Results**

- Used to evaluate the impact of clinical and demographic factors on **time-to-sepsis onset**.  
- Significant predictors: **heart rate**, **oxygen saturation**, **triage acuity**, **transport mode (ambulance)**, and **triage respiratory rate**

- **Model**: `lifelines.CoxPHFitter`
- **Duration Column**: `duration_hrs`
- **Event Column**: `event`
- **Baseline Estimation**: Breslow
- **Number of Observations**: 24,248
- **Number of Events Observed**: 24,248
- **Partial Log-Likelihood**: -219,904.26
- **Time Fit Was Run**: 2025-05-01 06:06:16 UTC

---

| **Variable**          | **coef** | **exp(coef)** | **se(coef)** | **coef lower 95%** | **coef upper 95%** | **exp(coef) lower 95%** | **exp(coef) upper 95%** | **z**    | **p**    | **-log2(p)** |
|-----------------------|----------|---------------|--------------|---------------------|---------------------|-------------------------|-------------------------|----------|----------|--------------|
| **gender_female**      | 0.03     | 1.03          | 0.01         | -0.00               | 0.05                | 1.00                    | 1.05                    | 1.86     | 0.06     | 4.00         |
| **transport_ambulance**| -0.16    | 0.86          | 0.01         | -0.18               | -0.13               | 0.83                    | 0.88                    | -11.78   | <0.005   | 103.94       |
| **triage_hr**          | 0.00     | 1.00          | 0.00         | 0.00                | 0.00                | 1.00                    | 1.00                    | 7.70     | <0.005   | 46.02        |
| **triage_rr**          | 0.07     | 1.07          | 0.00         | 0.07                | 0.08                | 1.07                    | 1.08                    | 29.63    | <0.005   | 638.49       |
| **triage_sbp**         | -0.00    | 1.00          | 0.00         | -0.00               | -0.00               | 1.00                    | 1.00                    | -14.25   | <0.005   | 150.58       |
| **triage_dbp**         | -0.00    | 1.00          | 0.00         | -0.00               | 0.00                | 1.00                    | 1.00                    | -1.92    | 0.05     | 4.20         |
| **triage_o2sat**       | -0.01    | 0.99          | 0.00         | -0.02               | -0.01               | 0.98                    | 0.99                    | -3.91    | <0.005   | 13.43        |
| **triage_acuity**      | -0.07    | 0.93          | 0.01         | -0.09               | -0.05               | 0.91                    | 0.95                    | -6.13    | <0.005   | 30.13        |

---

- **Concordance**: 0.55
- **Partial AIC**: 439,824.52
- **Log-Likelihood Ratio Test**: 1327.37 on 8 df
- **-log2(p) of ll-ratio test**: 931.95

---

### ⏳ Kaplan-Meier Estimates
- 🔺 High heart rate, 🔻 low oxygen saturation, 🚑 ambulance transport, and high triage acuity are associated with faster sepsis onset.

- These insights support early monitoring of key vitals and clinical presentation during the critical first 10–20 hours.
  
<img width="606" alt="image" src="https://github.com/user-attachments/assets/bc542199-c6a0-4f87-8fa5-068ff8113af5" />


---

### 🧩 Risk Stratification
- 📊 Cox model and Kaplan-Meier curves identify patients with a rapid decline in survival within the first 10–20 hours

---

### 🎯 Targeted Interventions
- 🚨 Prioritize care for patients arriving with high triage acuity, as they show faster sepsis progression

---

## 🔭 Future Work
- ⏱️ Implement **censoring** for patients who don’t develop sepsis during observation.  
- 📊 Build **real-time dashboards** to help ED staff flag high-risk patients quickly.

---

## ✅ Conclusion
- Based on survival analysis (Cox models & Kaplan-Meier curves):

- 🔍 Enables earlier and more accurate detection of high-risk patients, especially within the first 10 hours

- 💉 Supports timely, targeted interventions guided by vital signs and clinical presentation

---

## 📚 References
1. Johnson, A., Bulgarelli, L., Pollard, T., Gow, B., Moody, B., Horng, S., Celi, L. A., & Mark, R. (2024). MIMIC-IV (version 3.1). PhysioNet. https://doi.org/10.13026/kpb9-mt58.
2. Johnson, A.E.W., Bulgarelli, L., Shen, L. et al. MIMIC-IV, a freely accessible electronic health record dataset. Sci Data 10, 1 (2023). https://doi.org/10.1038/s41597-022-01899-x
3. Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., ... & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation [Online]. 101 (23), pp. e215–e220.


