# Pulse Rate Estimation Project

## Overview

This project was developed as part of the courses **Wearable Data Starter** and **AI for Healthcare**.  
The focus is on estimating pulse rate from wearable sensor data (PPG and accelerometer) using signal processing and machine learning techniques.

The algorithm processes data from the Troika dataset, which includes synchronized PPG, accelerometer, and reference ECG heart rate signals.

The goal is to accurately estimate heart rate during physical activities such as treadmill running, while accounting for motion artifacts using accelerometer information.

---

## Code Description

- **LoadTroikaDataset()**: Retrieves file paths for PPG and reference data files.
- **LoadTroikaDataFile(data_fl)**: Loads PPG and accelerometer signals from a `.mat` file.
- **bandpass_filter(signal, fs, lowcut=0.67, highcut=4.0, order=4)**: Applies a Butterworth bandpass filter to isolate physiological heart rate frequencies (40-240 BPM).
- **RunPulseRateAlgorithm(data_fl, ref_fl)**: Main function estimating pulse rate and confidence scores using FFT on sliding windows of filtered PPG and accelerometer data.
- **Evaluate()**: Runs the algorithm on the dataset and computes the mean absolute error (MAE) at 90% availability.
- **Visualization functions**: Plot raw signals, spectrograms, estimated vs. reference pulse rates, and MAE vs. availability curves.

---

## Dataset Description

The Troika dataset contains synchronized PPG, tri-axis accelerometer, and reference ECG heart rate data sampled at 125 Hz. Data were collected during treadmill running at varying speeds.

**Limitations:**

- Focused on treadmill running; limited real-world activity diversity.
- Limited subject diversity may affect generalizability.
- Motion artifacts occur mainly during activity transitions.

**Recommendations for more complete datasets:**

- Include diverse activities (walking, cycling, daily living).
- Increase subject demographic diversity.
- Longer recordings in varied environments.
- Multi-modal sensor data (additional PPG, ECG, respiratory signals).

**Sources:**

- Troika Dataset official documentation and README files.
- Relevant scientific literature on PPG-based heart rate estimation and motion artifact challenges.
- Common best practices in biomedical signal processing and wearable sensor data collection.

---

## Algorithm Summary

- Uses sliding 8-second windows with 2-second steps.
- Detects dominant frequency in PPG FFT within physiological band.
- Uses accelerometer FFT to detect motion artifacts and adjust confidence.
- Applies a physiological constraint limiting heart rate changes to 3 BPM per window.
- Outputs pulse rate estimates and confidence scores at 2-second intervals.

---

## Performance

- Evaluated on Troika dataset using train-test splits.
- Achieves MAE < 15 BPM at 90% availability.
- Performance may vary on other datasets or activities.
- Visualizations support interpretation of results and confidence.

---

## Usage Instructions

1. Clone or download the repository.
2. Install required Python packages (`numpy`, `scipy`, `matplotlib`, etc.).
3. Place the Troika dataset files in the specified folder.
4. Run the notebook or script to load data, run the algorithm, and generate visualizations.
5. Use `Evaluate()` to compute overall performance metrics.

---

## Contact

For questions or support, please contact [Your Name] at [your.email@example.com].

---

## References

- Troika Dataset official documentation.
- Zhang et al., "Troika: A General Framework for Heart Rate Monitoring Using Wrist-Type Photoplethysmographic Signals During Intensive Physical Exercise," IEEE Transactions on Biomedical Engineering, 2015.
- Temko et al., "PPG-Based Heart Rate Monitoring During Physical Exercise Using Wiener Filtering and Random Forest Regression," IEEE Transactions on Biomedical Engineering, 2015.

---

*This project was developed as part of the Wearable Data Starter and AI for Healthcare courses.*
