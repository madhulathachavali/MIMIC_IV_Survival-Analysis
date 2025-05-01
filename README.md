# Time-to-Event (Survival) Analysis for Sepsis Onset using MIMIC-IV-ED.

## 1. Introduction

Dataset used in this analysis is from MIMIC-IV-ED, a large, deidentified dataset of emergency department stays (2011–2019) at Beth Israel Deaconess Medical Center, including vital signs, triage, medications, and diagnoses, obtained via PhysioNet.
References: 
 1. Johnson, A., Bulgarelli, L., Pollard, T., Celi, L. A., Mark, R., & Horng, S. (2023). MIMIC-IV-ED (version 2.2). PhysioNet. https://doi.org/10.13026/5ntk-km72.
 2. Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., ... & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation [Online]. 101 (23), pp. e215–e220.

## 2. Applied survival analysis and Cox Proportional Hazards model to assess factors influencing readmissions.
- Censoring data
- Cox Proportional Hazards Model
- Vital Signs Impact
- Demographics and Comorbidities

  2.1 Cox Proportional Hazards Model
Cox Proportional Hazards model was used to identify factors associated with time-to-onset of sepsis after emergency department admission. The model estimates hazard ratios for each covariate, to understand clinical and demographic variables impact on the likelihood of sepsis onset over time.

 Features used in the model:

- Demographics: gender, race
  
  ### Sepsis Distribution by Race

| Race                                         | No Sepsis (0) | Sepsis (1) |
|----------------------------------------------|---------------|------------|
| AMERICAN INDIAN/ALASKA NATIVE               | x             | 65         |
| ASIAN                                        | x             | 319        |
| ASIAN - ASIAN INDIAN                         | x             | 17         |
| ASIAN - CHINESE                              | x             | 79         |
| ASIAN - KOREAN                               | x             | 5          |
| ASIAN - SOUTH EAST ASIAN                     | x             | 27         |
| BLACK/AFRICAN                                | x             | 49         |
| BLACK/AFRICAN AMERICAN                       | x             | 4271       |
| BLACK/CAPE VERDEAN                           | x             | 71         |
| BLACK/CARIBBEAN ISLAND                       | x             | 148        |
| HISPANIC OR LATINO                           | x             | 21         |
| HISPANIC/LATINO - CENTRAL AMERICAN           | x             | 44         |
| HISPANIC/LATINO - COLUMBIAN                  | x             | 64         |
| HISPANIC/LATINO - CUBAN                      | x             | 111        |
| HISPANIC/LATINO - DOMINICAN                  | x             | 518        |
| HISPANIC/LATINO - GUATEMALAN                 | x             | 75         |
| HISPANIC/LATINO - HONDURAN                   | x             | 24         |
| HISPANIC/LATINO - MEXICAN                    | x             | 25         |
| HISPANIC/LATINO - PUERTO RICAN               | x             | 1589       |
| HISPANIC/LATINO - SALVADORAN                | x             | 145        |
| MULTIPLE RACE/ETHNICITY                      | x             | 1          |
| NATIVE HAWAIIAN OR OTHER PACIFIC ISLANDER    | x             | 19         |
| OTHER                                        | x             | 1930       |
| PATIENT DECLINED TO ANSWER                   | x             | 16         |
| PORTUGUESE                                   | x             | 25         |
| SOUTH AMERICAN                               | x             | 7          |
| UNKNOWN                                       | x             | 69         |
| WHITE                                         | x             | 15826      |
| WHITE - BRAZILIAN                            | x             | 8          |
| WHITE - EASTERN EUROPEAN                     | x             | 43         |
| WHITE - OTHER EUROPEAN                       | x             | 496        |
| WHITE - RUSSIAN                               | x             | 305        |


- Vital signs: triage_hr, triage_rr, triage_o2sat, triage_sbp, triage_dbp, vitals_hr, vitals_rr, etc.

- Clinical factors: arrival_transport, triage_acuity, and ED duration_hrs

2.2 Censoring (Future Work)
Censoring helps account for patients who didn’t develop sepsis during the observation period. It’s not included in this version but is planned for future updates to better handle incomplete follow-up or early discharges.

2.3 Vital Signs Impact

2.4 Demographics and Comorbidities
  
## 4. Results developed a risk score to stratify patients.
-  Stratification ( based on sepsis)
-  Key Predictors
-  Actionable Outcome

## 5. Outcome: Improved hospital management by identifying high-risk patients and improving readmission prevention strategies.
- Impact on Patient Care
- Operational Efficiency
