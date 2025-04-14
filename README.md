# 🛡️ Network Intrusion Detection System (NIDS)

## 🧠 Objective
To build a Network Intrusion Detection System (NIDS) that detects and classifies network intrusions using K-Nearest Neighbors (KNN). The goal is to identify whether a connection is normal or an attack (binary classification) and determine the type of attack (multiclass classification).

## 📄 Overview
With the rising threat of cyber-attacks, real-time detection of malicious activities is essential for securing digital infrastructure. This project implements a machine learning approach using KNN to classify network activities based on a rich set of features extracted from connection logs.

## 📊 Dataset Used
The dataset comprises network activity logs collected over time, categorized into 11 types of attacks and normal activities. Each file corresponds to a specific attack or normal behavior:
- `Data_of_Attack_Back_Normal`
- `Data_of_Attack_Back`
- `Data_of_Attack_Back_BufferOverflow`
- `Data_of_Attack_Back_FTPWrite`
- `Data_of_Attack_Back_GuessPassword`
- `Data_of_Attack_Back_Neptune`
- `Data_of_Attack_Back_NMap`
- `Data_of_Attack_Back_PortSweep`
- `Data_of_Attack_Back_RootKit`
- `Data_of_Attack_Back_Satan`
- `Data_of_Attack_Back_Smurf`

Each file has the same structure and includes 41 features describing connection statistics.

## ❓ Questions Addressed
1. Can we accurately classify if a network activity is normal or an attack using KNN?
2. Can we detect the specific type of attack among the 11 types?
3. What features are most helpful in differentiating normal and abnormal behavior?

## 🔄 Process
- **Data Loading & Integration**: Combined all 11 datasets and added a new `attack_type` column based on the source file.
- **Resampling**: Performed resampling to balance the class distribution.
- **Feature Engineering**: Encoded categorical features and normalized numerical features.
- **Binary Classification**: Labeled data as either `normal` or `attack`.
- **Multiclass Classification**: Kept detailed labels for each specific attack type.
- **Modeling with KNN**:
  - Tuned `k` using cross-validation.
  - Evaluated performance using accuracy, confusion matrix, and classification report.

## 🔍 Key Insights
- KNN can perform well on intrusion detection tasks, especially for binary classification.
- Proper preprocessing and feature normalization greatly improve KNN performance.
- The model showed reasonable accuracy in identifying common attacks like `neptune`, `smurf`, and `back`.
- Some rare attacks were harder to detect due to class imbalance, highlighting the importance of resampling.

## 📤 Outputs
- Trained KNN model for both binary and multiclass classification.
- Evaluation reports including:
  - Accuracy scores
  - Confusion matrices
  - Classification reports (Precision, Recall, F1-score)
- Graphs (optional): Elbow curve for selecting optimal `k`.
