Fetal PCG Anomaly Detection Using LSTM Autoencoder

This project detects anomalies in fetal phonocardiogram (PCG) signals using an LSTM Autoencoder.
Since the dataset is unlabeled, we apply self-supervised learning to detect abnormal heartbeats without manual labels.

Project Overview:
Dataset: Fetal PCG signals from PhysioNet
Model: LSTM Autoencoder for time-series anomaly detection
Thresholding: Interquartile Range (IQR) for anomaly detection
Decision Rule: If >10% of sequences exceed threshold → classify as Anomalous

Methodology
1. Data Preprocessing
Convert Elapsed Time to datetime format
Resample the PCG signal into 10-second windows
Normalize data

2. Creating Time Sequences
Convert PCG signals into overlapping sequences of 10 seconds
Prepare training & testing datasets

3. Training LSTM Autoencoder
Train an LSTM Autoencoder to reconstruct normal patterns
Reconstruction error is used for anomaly detection

4. Anomaly Detection Using IQR
Compute Reconstruction Error for each sequence
Use Interquartile Range (IQR) to dynamically set an anomaly threshold
Formula: Threshold = Q3 + 1.5 * IQR

5. Final Decision Rule
If >10% of sequences exceed the threshold → classify as Anomalous
Else, classify as Normal

Results & Findings
The model learns normal fetal PCG patterns
Higher reconstruction errors indicate anomalies
IQR-based thresholding dynamically detects anomalies

Dataset
⚠️ Dataset is NOT included in this repository. Please download it manually from:
🔗https://physionet.org/content/fpcgdb/1.0.0/

Author
👤 Kommuri Varshitha
🔗 LinkedIn: https://linkedin.com/in/kommurivarshitha04





