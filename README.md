# Functional Principal Component Analysis of HRV Recovery Trajectories in Endurance Athletes

**Author:** Gabriel Della Mattia  
**Date:** August 16, 2019  

## Abstract

Heart rate variability (HRV) dynamics following training sessions provide insight into the balance between physiological stress and recovery. Traditional approaches often reduce HRV to scalar summaries, overlooking the information contained in the full recovery trajectory. This study applies **Functional Principal Component Analysis (FPCA)** to HRV recovery profiles, enabling multidimensional characterization of features such as depth of suppression, speed of return, and potential overshoot.

<a href="https://enydog.github.io/HRV-Recovery-FPCA/" target="_blank">
  <img src="https://img.shields.io/badge/Open-Sandbox-blue?style=for-the-badge">
</a>

<a href="https://drive.google.com/file/d/1Kpljz_HxjaXxfC4xYYauMLlOLxZH0q1J/view?usp=sharing" target="_blank">
  <img src="https://img.shields.io/badge/Open-White%20Paper-red?style=for-the-badge">
</a>

<a href="https://www.facebook.com/photo/?fbid=10156730878943553&set=a.106898123552" target="_blank">
  <img src="https://img.shields.io/badge/Those%20were%20good%20times%20working%20in%20California.-green?style=for-the-badge">
</a>


---

## Introduction

Heart rate variability (HRV), commonly quantified through the root mean square of successive differences (rMSSD), typically decreases immediately after exercise and then returns toward baseline with varying shapes and time courses. Treating these recovery profiles as continuous functions, rather than discrete endpoints, allows for deeper physiological interpretation.  

This work integrates an educational simulator for conceptual visualization with empirical analyses performed on AGMT2 Team athletes. Unless explicitly indicated as sandbox illustration, all reported results derive from real athlete data.

---

## Mathematical Framework

Let **Xi(t)** denote the HRV recovery trajectory of athlete *i* over time *t ∈ [0, T]* after a training session.  

- FPCA expands each trajectory as:


- **µ(t):** functional mean  
- **ϕk(t):** orthogonal eigenfunctions  
- **ξik:** subject-specific scores  
- **λk:** variance explained by each component  

---

## Physiological Interpretation

The leading FPCA modes map onto physiologically interpretable recovery features:

- **PC1 – Depth of suppression:** strong vs. mild post-exercise HRV depression  
- **PC2 – Recovery rate:** fast vs. slow return to baseline  
- **PC3 – Overshoot/rebound:** oscillatory or secondary dips during recovery  

---

## Data Acquisition and Preprocessing

### Wearable Logging  
- Devices: Garmin Forerunner FR955/FR965  
- Sampling: 1 HRV snapshot every 3 minutes (24h, 481 points/day)  
- Export: .FIT files → parsed offline to Parquet/CSV  

### Preprocessing Protocol  
1. Time normalization and segmentation  
2. Physiological range checks (10–250 ms)  
3. Successive-difference rule for artifacts  
4. Robust smoothing (Tukey biweight + Savitzky–Golay)  
5. Non-wear/shower detection  
6. Imputation for short gaps (<15 min)  
7. Final quality control (≥70% valid samples/day)  

### Reproducibility  
- Deterministic parsing and QC pipeline  
- Conservative thresholds fixed a priori  
- Sensitivity analyses confirm robustness  

---

## Dataset and Statistical Characterization

- **Cohort:** 35 competitive amateur triathletes (AGMT2 Team)  
- **Duration:** ~200 days per athlete  
- **Coverage:** ~7,000 athlete-days, >3.3 million HRV samples  

### Data Volume  
- 481 temporal samples per day (3-min resolution)  

### Temporal Consistency  
- >95% of days with complete coverage  
- Double-training days flagged for archetype analysis  

---

## FPCA Decomposition

HRV trajectories are expressed as:  


- First three components: suppression depth, recovery speed, rebound  
- Score scatter plots reveal clustering of recovery archetypes  

---

## Strengths and Limitations

**Strengths**  
- Large longitudinal dataset (~7,000 athlete-days)  
- Ecological validity under real-world conditions  
- High temporal resolution (3-min sampling)  
- Both intra- and inter-individual variability captured  

**Limitations**  
- Cohort limited to competitive amateur triathletes  
- HRV measured with wrist-worn devices (vs. ECG gold standard)  
- Narrow demographic distribution  
- No external validation yet performed  

---

## Applications

1. **Recovery archetypes:** classification of athletes by recovery profile  
2. **Training load monitoring:** detection of atypical recovery patterns  
3. **Predictive modeling:** FPCA-derived scores for machine learning applications  
4. **Performance context:** linking recovery archetypes to training outcomes  

---

## Conclusion

FPCA provides a rigorous and physiologically interpretable framework for analyzing HRV recovery dynamics in endurance athletes. By decomposing trajectories into orthogonal modes, latent processes such as suppression depth, recovery speed, and rebound are revealed—insights that scalar metrics cannot capture.  

All empirical findings are derived from AGMT2 Team athletes, ensuring real-world validity. The educational sandbox serves only as an illustrative tool.  

This approach demonstrates FPCA’s potential for both academic characterization of recovery heterogeneity and practical athlete monitoring. Future work should expand validation, integrate additional biomarkers, and explore predictive modeling for readiness-to-train applications.  

---

## References

- Ramsay, J. O., & Silverman, B. W. (2005). *Functional Data Analysis.* Springer.  
- Esco, M. R., & Flatt, A. A. (2021). Heart rate variability and endurance training adaptation: A review. *Sports, 9(6), 85.*



 
