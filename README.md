# Final-Project

# Pulse Rate Estimation and Clinical Analysis Project

## Overview

This project focuses on estimating pulse rate from wearable sensor data and analyzing clinically relevant heart rate trends in a cardiac patient population. It is developed as part of the **Wearable Data Starter** and **AI for Healthcare** courses offered by **Udacity**.

The project is divided into two main parts:

1. **Pulse Rate Estimation Algorithm (Part 1)**  
   Development and evaluation of a signal processing and machine learning algorithm to estimate heart rate from raw PPG and accelerometer signals using the Troika dataset.

2. **Clinical Application and Analysis (Part 2)**  
   Analysis of resting heart rate (RHR) trends using the CAST dataset, which contains 24-hour heart rate time series from patients post-myocardial infarction. The goal is to validate known clinical trends in RHR variation with age and sex using wearable-like heart rate data.

---

## Data Description

- **Troika Dataset:** Raw PPG and tri-axis accelerometer signals with ECG reference, collected during treadmill exercise.
- **CAST Dataset:** 24-hour heart rate time series from post-myocardial infarction patients, smoothed and resampled to resemble wearable PPG data. Includes metadata with age groups and sex.
- The heart rate data in CAST are pre-processed and resampled to resemble PPG-derived pulse rate signals.
- Resting heart rate is estimated as the 5th percentile of each subject’s 24-hour heart rate series, providing a robust measure of baseline cardiovascular status.
- **Note:** Raw PPG and accelerometer signals are not available in the CAST dataset; therefore, the pulse rate algorithm developed in Part 1 could not be applied directly on raw signals for further validation.

---

## Code Summary

- **Part 1:**  
  - Functions to load Troika dataset raw signals.  
  - Pulse rate estimation algorithm using bandpass filtering, FFT peak detection, and motion artifact mitigation.  
  - Evaluation using mean absolute error (MAE) at 90% availability.

- **Part 2:**  
  - Function `AgeAndRHR(metadata, filename)` to load heart rate time series for each subject, compute resting heart rate (5th percentile), and retrieve age group and sex from metadata.  
  - Construction of a DataFrame with `age_group`, `sex`, and `rhr`.  
  - Visualization scripts to analyze RHR distributions by age group and sex.  
  - Clinical analysis validating known physiological trends.

---

## Clinical Findings

- Women exhibit higher resting heart rates than men across all age groups.
- Resting heart rate increases until middle age and then decreases in older age groups, validating known physiological trends.
- Variability in RHR is greater among women, particularly in younger and middle-aged groups.

---

## Future Directions

- Incorporate additional clinical and lifestyle data to control for confounding factors.
- Use activity data to better isolate true resting periods.
- **Apply the pulse rate algorithm developed in Part 1 directly on raw PPG and accelerometer data for further validation, if such data become available.**
- Expand sample size and diversity to strengthen findings.

---

## Usage Instructions

1. Place the Troika and CAST dataset files and metadata in the designated folders.
2. Run the provided notebooks or scripts for Part 1 to estimate pulse rate and evaluate performance.
3. Run the notebooks or scripts for Part 2 to compute resting heart rate and analyze clinical trends.
4. Visualize results using provided plotting functions.
5. Review clinical conclusions and explore further analyses as needed.

---

## Project Team and Acknowledgments

This project was developed by **Anis Boubala**, veterinarian and aspiring data scientist for healthcare, as part of the **Wearable Data Starter** and **AI for Healthcare** courses offered by **Udacity**.



This repository will be shared with Laila Bellous and Yannis Pandis **exclusively for educational purposes**.  
No direct assistance was received from them during the development of this project.

The code and text have been reviewed, corrected, and improved with the help of AI tools.

All pedagogical content and datasets used in this project belong to **Udacity** and their respective licensors.

---

## Contact

For questions or collaboration, please contact:  
**Anis Boubala** – 

---

## References

- Zhang et al., "Troika: A General Framework for Heart Rate Monitoring Using Wrist-Type Photoplethysmographic Signals During Intensive Physical Exercise," IEEE Trans. Biomed. Eng., 2015.  
- Stein PK et al., "Clinical and demographic determinants of heart rate variability in patients post myocardial infarction," Clin Cardiol, 2000.  
- Goldberger AL et al., "PhysioBank, PhysioToolkit, and PhysioNet: Components of a New Research Resource for Complex Physiologic Signals," Circulation, 2000.  
- Additional references as cited in the project.

---

*This project demonstrates the integration of signal processing, machine learning, and clinical data analysis to advance wearable health monitoring technologies.*

