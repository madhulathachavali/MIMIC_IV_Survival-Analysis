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
- 🔺 High **heart rate** and 🔻 low **oxygen saturation** are associated with increased sepsis risk.

---

### 3️⃣ Clinical Factors
- 🚑 **Mode of arrival** (e.g., ambulance) and 🏥 **triage acuity** significantly influence sepsis risk.

---

## 📈 Survival Analysis Insights

### 📌 Cox Proportional Hazards Model
- Used to evaluate the impact of clinical and demographic factors on **time-to-sepsis onset**.  
- Significant predictors: **heart rate**, **oxygen saturation**, **triage acuity**, **gender**, and **race**.

---

### ⏳ Kaplan-Meier Estimates
- Kaplan-Meier survival curves estimate **time-to-sepsis** for different patient groups.  
- Helps visualize sepsis onset trends based on vitals and demographics.

---

### 🧩 Risk Stratification
- Monitoring key vitals and demographics enables early detection and **prioritized care** for high-risk patients.

---

### 🎯 Targeted Interventions
- Interventions based on **heart rate** and **oxygen saturation** at triage can improve sepsis management.

---

## 🔭 Future Work
- ⏱️ Implement **censoring** for patients who don’t develop sepsis during observation.  
- 📊 Build **real-time dashboards** to help ED staff flag high-risk patients quickly.

---

## ✅ Conclusion
Integrating these insights—especially from **survival analysis**—can lead to:  
- Improved **early detection** and **intervention**  
- Better **patient outcomes**  
- More **efficient ED operations**

---

## 📚 References
1. Johnson, A., Bulgarelli, L., Pollard, T., Gow, B., Moody, B., Horng, S., Celi, L. A., & Mark, R. (2024). MIMIC-IV (version 3.1). PhysioNet. https://doi.org/10.13026/kpb9-mt58.
2. Johnson, A.E.W., Bulgarelli, L., Shen, L. et al. MIMIC-IV, a freely accessible electronic health record dataset. Sci Data 10, 1 (2023). https://doi.org/10.1038/s41597-022-01899-x
3. Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., ... & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation [Online]. 101 (23), pp. e215–e220.


