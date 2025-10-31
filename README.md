# Modelling Human Activity States Using Hidden Markov Models

## 1. Project Overview

This project implements a Hidden Markov Model (HMM) to classify four fundamental human activities (Standing, Walking, Jumping, and Still) based on time-series data collected from smartphone inertial sensors (Accelerometer and Gyroscope).

The model is trained to learn the characteristic feature patterns of each activity, as well as the probabilistic transitions between them.

**Unique Group Use Case:** The primary motivation for this project is to develop a robust prototype for **Fall Prevention and Elderly Care Monitoring**. The HMM structure is ideal for distinguishing normal activity sequences from abrupt, anomalous transitions indicative of a potential fall.


## 2. Project Deliverables and Tasks 
The repository contains the final deliverables required for the assignment:

| Project Task | Member Responsible | Contribution Focus |
| :--- | :--- | :--- |
| **Task 1** | **Both** | Data Collection (51 Samples) & Rate Harmonization |
| **Task 2** | **You** | Feature Extraction (22 Features) & Normalization |
| **Task 3** | **You** | HMM Model Definition (States, Observations, Structure) |
| **Task 4** | **Benitha** | HMM Implementation (Baum–Welch & Viterbi Algorithms) |
| **Task 5** | **Benitha** | Model Evaluation (Testing on Unseen Data & Metrics) |
| **Task 6** | **Both** | Analysis, Discussion, and Report Writing |

### Deliverables:

1.  **`/dataset/`**: Directory containing the $\mathbf{51}$ cleaned, labeled samples (folders of calibrated Accelerometer and Gyroscope CSVs).
2.  **` Hidden_Markov_Model.ipynb`**: The main Python notebook containing the full implementation of Tasks 2-5, including feature extraction, HMM training, evaluation, and visualizations.
3.  **`Report.pdf`**: The final project report (4-5 pages) detailing methodology, results, and discussion.

### Task Allocation and Contribution 
The project's tasks were divided equally, ensuring a balanced contribution.
| Project Task | Member Contribution | Contribtuion focus|
| :---  | :---  | :--- 

| **Task 1** | **Both** | Data Collection (51 Samples) & Rate Harmonization |
| **Task 2** | **Tamanda** | Feature Extraction (22 Features) & Normalization |
| **Task 3** | **Tamanda** | HMM Model Definition (States, Observations, Structure) |
| **Task 4** | **Benitha** | HMM Implementation (Baum–Welch & Viterbi Algorithms) |
| **Task 5** | **Benitha** | Model Evaluation (Testing on Unseen Data & Metrics) |
| **Task 6** | **Both** | Analysis, Discussion, and Report Writing |


## 3. Data Collection Summary (Task 1)

The training data consists of 51 samples, each 10 seconds in duration, recorded at a **harmonized sampling rate of 100 Hz**.

c | 16 | 160 seconds |
| **Standing** | 12 | 120 seconds |
| **Still** | 12 | 120 seconds |
| **Jumping** | 11 | 110 seconds |

---

## 4. Feature Extraction Details (Task 2)

Each 10-second sample (window) was converted into a $\mathbf{22 \text{-dimensional feature vector}}$ using the following derived metrics:

* **Time-Domain (12 features):** Mean and Standard Deviation ($\sigma$) for all 6 sensor axes.
* **Magnitude (1 feature):** Signal Magnitude Area (SMA) derived from Accelerometer data.
* **Correlation (3 features):** Pearson Correlation between the $\text{Acc}_x, \text{Acc}_y, \text{Acc}_z$ axes.
* **Frequency-Domain (6 features):** Dominant Frequency derived from **Fast Fourier Transform (FFT)** for all 6 sensor axes.

All 22 features were standardized using **Z-score normalization** before model training.

## 5. HMM Structure
##. Set Up and Execution
### Prerequisites
 * Python 3.8
 * Required libraries: `pandas, scipy, scikit-learn, matplotlib, seaborn,  **hmmlearn** `

## Running the Notebook
1. Clone this repository
2. Open the `Hidden_Markov_Model.ipynb`  in Google Colab or your preferred environment.
3. Confire the `DRIVE_PATH` variable in the notebook to redirect to the location of the dataset.
4. Execute all the cells sequentially to reproduce the HMM training, evaluation, and visualizations.
 
