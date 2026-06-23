# Sleep Apnea Detection
Multi-signal detection using ECG, EEG, and Respiratory signals.

## Dataset
MIT-BIH Polysomnographic Database (PhysioNet)
- 5 patients: slp01a, slp02a, slp03, slp04, slp14
- 23 hours of overnight sleep recordings
- 2754 windows of 30 seconds each
- 2389 normal windows, 365 apnea windows

## Signals
- **ECG** (Electrocardiogram) — Eman's focus
- **EEG** (Electroencephalogram) — Amna's focus
- **Respiratory** — Both

## Models
- Random Forest — 88.75% accuracy, AUC 0.891
- XGBoost — 88.75% accuracy
- 1D-CNN on raw ECG — 87% accuracy, AUC 0.88

## Key Finding
CNN probability (cnn_prob) was the #1 most important feature
in both Random Forest and XGBoost independently, confirming
that deep learning on raw ECG signals captures information
that hand-crafted features alone cannot fully represent.

## Ablation Study Results
| Signal Combination | Accuracy | F1-Score | AUC |
|---|---|---|---|
| ECG only | 87.48% | 0.582 | 0.879 |
| EEG only | 80.22% | 0.441 | 0.796 |
| Respiratory only | 85.12% | 0.512 | 0.826 |
| ECG + EEG | 86.39% | 0.540 | 0.881 |
| ECG + Respiratory | 88.93% | 0.621 | 0.878 |
| EEG + Respiratory | 88.20% | 0.570 | 0.866 |
| All 3 Signals | 88.75% | 0.587 | 0.891 |

## Team
- Eman (ECG + CNN + Random Forest + Evaluation)
- Amna (EEG + Respiratory + XGBoost + Feature Importance)

## Repository Structure

sleep-apnea-detection/

├── eman/

│   ├── ecg_exploration.ipynb

│   ├── ecg_segmentation.ipynb

│   ├── ecg_feature_extraction.ipynb

│   ├── ecg_cnn_model.ipynb

│   ├── feature_fusion.ipynb

│   ├── model_random_forest.ipynb

│   └── model_evaluation.ipynb

├── amna/

│   ├── amna_eeg_exploration.ipynb

│   ├── eeg_segmentation.ipynb

│   ├── eeg_feature_extraction.ipynb

│   ├── respiratory_feature_extraction.ipynb

│   ├── model_xgboost.ipynb

│   └── feature_importance_comparison.ipynb


## B.Sc. Data Science and Artificial Intelligence
Indian Institute of Technology Guwahati