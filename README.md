# HRV Recovery Analysis with Functional PCA (FPCA)

Este repositorio contiene el código, simulaciones y documentación asociada al análisis de **recuperación de la variabilidad de la frecuencia cardíaca (HRV)** usando **Functional Principal Component Analysis (FPCA)**.  
El objetivo es proveer un marco matemático y visual para entender cómo responden distintos atletas al estrés de un entrenamiento y cómo se recuperan.

---

## 📖 Descripción
La **HRV** (habitualmente medida como *rMSSD*) cae luego de una sesión de entrenamiento y retorna gradualmente a su línea de base.  
Los métodos tradicionales suelen reducir esta dinámica a un valor escalar (ej. diferencia pre vs. post entrenamiento), perdiendo información de la **curva completa de recuperación**.  

La **FPCA** permite:
- Descomponer las curvas de recuperación en componentes ortogonales.
- Identificar patrones fisiológicos como:
  - **Magnitud de la caída inicial**
  - **Velocidad de recuperación**
  - **Rebote u overshoot**

---

## 🧮 Marco Matemático
Dada la trayectoria de HRV de un atleta \( X_i(t) \):

\[
X_i(t) = \mu(t) + \sum_{k=1}^{K} \xi_{ik} \, \phi_k(t)
\]

- \( \mu(t) \): curva media de recuperación.  
- \( \phi_k(t) \): funciones ortogonales (modos principales).  
- \( \xi_{ik} \): puntuaciones específicas de cada atleta (firma numérica en el espacio FPCA).  

Cada modo tiene interpretación fisiológica:
1. **PC1** – Profundidad de la caída.  
2. **PC2** – Velocidad de recuperación.  
3. **PC3** – Rebote / oscilación.  

---

## 🎛️ Sandbox Interactivo
Incluye un simulador HTML/JS donde se pueden manipular parámetros de las curvas sintéticas y observar cómo se modifican los componentes de la FPCA en tiempo real.

**Controles principales:**
- `Drop sharpness`: modifica la constante exponencial \( \alpha \), controlando la caída inicial.  
- `Overshoot rate` y `Overshoot amplitude`: añaden componente sinusoidal \( B e^{-\gamma t}\sin(\beta t) \).  
- `Random seed`: controla la variabilidad estocástica \( \epsilon(t) \).  
- `Number of curves`: define el tamaño del grupo de simulación \( N \).  

<a href="https://enydog.github.io/HRV-Recovery-FPCA/" target="_blank">
  <img src="https://img.shields.io/badge/Open-Sandbox-blue?style=for-the-badge">
</a>
 

---

## 📊 Visualizaciones
El repositorio incluye:
- Curvas sintéticas de recuperación HRV con curva media resaltada.  
- Descomposición FPCA mostrando:
  - Varianza explicada por cada componente.  
  - Distribución de atletas en el espacio PC1–PC2.  
  - Reconstrucciones animadas de trayectorias.  

---

## 🚀 Aplicaciones
- Identificación de **arquetipos de recuperación** (rápida vs. lenta, con o sin rebote).  
- Monitoreo de **carga de entrenamiento** y detección de maladaptación.  
- Modelos personalizados de **predicción de readiness** usando scores FPCA.  

---

## 📚 Referencias
- Ramsay, J. O., & Silverman, B. W. (2005). *Functional Data Analysis*. Springer.  
- Esco, M. R., & Flatt, A. A. (2021). *Heart rate variability and endurance training adaptation: A review*. Sports, 9(6), 85.  

---

## 👤 Autor
**Gabriel Della Mattia**  
Ingeniero y científico de datos especializado en deporte de resistencia.  

---

## 📄 Licencia
Este proyecto está bajo licencia MIT. Puedes usarlo y adaptarlo libremente, citando la fuente.
