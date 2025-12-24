German Credit Risk Prediction (Machine Learning)
📌 Project Overview
This project builds an end-to-end credit risk classification system using the German Credit dataset.
The goal is to predict whether a loan applicant represents a good or bad credit risk, with a strong focus on business-relevant evaluation metrics rather than accuracy alone.
In banking, missing defaulters is far more costly than rejecting some good customers.
This project reflects that reality by prioritising recall for defaulters and explicitly analysing trade-offs.
🏦 Business Problem
Banks must decide whether to approve or reject loan applications based on customer information available at decision time.
Key objectives:
Identify high-risk customers likely to default
Minimise financial loss from missed defaulters
Maintain explainability and regulatory suitability
📊 Dataset
German Credit Risk Dataset
1,000 loan applicants
20 input features (numeric + categorical)
Binary target:
good → likely to repay
bad → likely to default
⚙️ Project Workflow
Business problem definition
Data loading and inspection
Exploratory analysis (risk drivers)
Feature encoding (one-hot encoding)
Train/test split with stratification
Baseline model (Logistic Regression)
Threshold optimisation for recall
Tree-based model (Decision Tree)
Evaluation using confusion matrix, recall, ROC, and AUC
Model persistence (joblib)
📈 Models Used
Logistic Regression
Baseline, interpretable, regulator-friendly
Decision Tree
Captures non-linear risk patterns
Optimised for high recall of defaulters
📐 Evaluation Strategy
Instead of relying on accuracy, the project focuses on:
Recall (Bad customers) — primary metric
Confusion Matrix — error analysis
ROC Curve & AUC — overall discrimination power
📊 Model Performance Summary
Model	Recall (Bad)	False Positives	AUC
Logistic Regression (default threshold)	~0.46	29	~0.69
Logistic Regression (threshold tuned)	~0.70	↑	~0.69
Decision Tree	~0.83	72	0.71
🧠 Key Insights
Accuracy alone is misleading due to class imbalance (~70% good customers)
Threshold tuning significantly improves recall without changing the model
Decision Trees capture complex interactions and outperform Logistic Regression in recall
Higher false positives are an acceptable trade-off to reduce costly defaults
This mirrors real-world banking risk management practices
💾 Saved Models
Trained models are saved for reproducibility and reuse:
models/logistic_regression.joblib
models/decision_tree.joblib
models/threshold.joblib
🧪 Visual Outputs
ROC curve with AUC score saved in reports/
High-resolution plots suitable for documentation and presentations
🛠️ Tech Stack
Python
Pandas, NumPy
scikit-learn
Matplotlib
joblib
🚀 Conclusion
This project demonstrates how machine learning models should be evaluated and selected based on business cost, not just technical performance.
The final recommendation prioritises defaulter detection, aligning the solution with real banking objectives.

Metrics Comparison Table (standalone)
| Model | Recall (Bad) | False Positives | AUC | Business Interpretation |
|-----|-------------|----------------|-----|-------------------------|
| Logistic Regression | 0.46 | 29 | 0.69 | Misses many defaulters, unsafe for banking |
| Logistic Regression (tuned) | 0.70 | Higher | 0.69 | Improved risk capture via threshold tuning |
| Decision Tree | 0.83 | 72 | 0.71 | Best defaulter detection, acceptable trade-off |



👤 Author
Muhammad Shaan
MSc Computer Science (Data Analytics)
Carlisle, UK


