# Clinical Application - Resting Heart Rate Analysis

## Overview

This part of the project analyzes resting heart rate (RHR) data derived from the CAST dataset, which contains 24-hour heart rate time series from approximately 1500 subjects post-myocardial infarction. The goal is to validate known clinical trends in RHR variation with age and sex using wearable-like heart rate data.

---

## Data Description

- The heart rate data are pre-processed and resampled to resemble PPG-derived pulse rate signals.
- Metadata includes subject age groups and sex.
- Resting heart rate is estimated as the 5th percentile of each subject’s 24-hour heart rate series, providing a robust measure of baseline cardiovascular status.
- **Note:** Raw PPG and accelerometer signals are not available in this dataset; therefore, the pulse rate algorithm developed in Part 1 could not be applied directly on raw signals for further validation.

---

## Code Summary

- **AgeAndRHR(metadata, filename)**: Loads heart rate data for each subject, computes RHR as the 5th percentile, and retrieves age group and sex from metadata.
- Constructs a DataFrame with columns: `age_group`, `sex`, and `rhr`.
- Visualization scripts plot RHR distributions by age group and sex.

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

1. Place the CAST dataset files and metadata in the designated folder.
2. Run the provided notebook or scripts to compute resting heart rate and generate visualizations.
3. Review clinical conclusions and explore further analyses as needed.

---

*This clinical analysis was developed as part of the Wearable Data Starter and AI for Healthcare courses.*

---

## References

- Stein PK, Domitrovich PP, Kleiger RE, Schechtman KB, Rottman JN. Clinical and demographic determinants of heart rate variability in patients post myocardial infarction: insights from the Cardiac Arrhythmia Suppression Trial (CAST). Clin Cardiol 23(3):187-94; 2000.
- Goldberger AL, Amaral LAN, Glass L, Hausdorff JM, Ivanov PCh, Mark RG, Mietus JE, Moody GB, Peng C-K, Stanley HE. PhysioBank, PhysioToolkit, and PhysioNet: Components of a New Research Resource for Complex Physiologic Signals. Circulation. 101(23):e215-e220; 2000.
- Additional references as relevant.
