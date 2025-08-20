# HRV Recovery Analysis with Functional PCA (FPCA)

This repository contains the code, simulations, and documentation for analyzing **heart rate variability (HRV) recovery** using **Functional Principal Component Analysis (FPCA)**.  
The goal is to provide a mathematical and visual framework to better understand how different athletes respond to training stress and how they recover.

---

## 📖 Description
**HRV** (commonly measured as *rMSSD*) drops after a training session and gradually returns to baseline.  
Traditional methods often reduce this dynamic to a scalar value (e.g., pre vs. post difference), losing valuable information from the **entire recovery curve**.  

**FPCA** allows:
- Decomposition of recovery curves into orthogonal components.
- Identification of physiological patterns such as:
  - **Magnitude of the initial drop**
  - **Speed of recovery**
  - **Rebound or overshoot**

---

## 🧮 Mathematical Framework
Given the HRV recovery trajectory of an athlete \( X_i(t) \):

\[
X_i(t) = \mu(t) + \sum_{k=1}^{K} \xi_{ik} \, \phi_k(t)
\]

- \( \mu(t) \): mean recovery curve.  
- \( \phi_k(t) \): orthogonal functions (principal modes).  
- \( \xi_{ik} \): subject-specific FPCA scores (numerical signature in FPCA space).  

Each mode has a physiological interpretation:
1. **PC1** – Depth of the initial drop.  
2. **PC2** – Speed of recovery.  
3. **PC3** – Rebound / oscillation.  

---

## 🎛️ Interactive Sandbox
Includes an HTML/JS simulator where users can manipulate parameters of synthetic curves and observe how FPCA components change in real time.

**Main controls:**
- `Drop sharpness`: modifies the exponential constant \( \alpha \), controlling the initial drop.  
- `Overshoot rate` and `Overshoot amplitude`: add a sinusoidal component \( B e^{-\gamma t}\sin(\beta t) \).  
- `Random seed`: controls stochastic variability \( \epsilon(t) \).  
- `Number of curves`: defines the group size for simulation \( N \).  

<a href="https://enydog.github.io/HRV-Recovery-FPCA/" target="_blank">
  <img src="https://img.shields.io/badge/Open-Sandbox-blue?style=for-the-badge">
</a>
 
---

## 📊 Visualizations
The repository includes:
- Synthetic HRV recovery curves with highlighted mean curve.  
- FPCA decomposition showing:
  - Variance explained by each component.  
  - Distribution of athletes in the PC1–PC2 space.  
  - Animated reconstructions of trajectories.  

---

## 🚀 Applications
- Identification of **recovery archetypes** (fast vs. slow, with or without rebound).  
- Monitoring **training load** and detecting maladaptation.  
- Personalized **readiness prediction models** using FPCA scores.  

---

## 📚 References
- Ramsay, J. O., & Silverman, B. W. (2005). *Functional Data Analysis*. Springer.  
- Esco, M. R., & Flatt, A. A. (2021). *Heart rate variability and endurance training adaptation: A review*. Sports, 9(6), 85.  

---

## 👤 Author
**Gabriel Della Mattia**  
Engineer and data scientist specialized in endurance sports.  

---

## 📄 License
This project is licensed under the MIT License. You are free to use and adapt it, provided you cite the source.
