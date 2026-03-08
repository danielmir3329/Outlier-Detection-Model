# AI Log Guardian: Multi-Model Anomaly Detection for System Monitoring

## Overview
This project implements a **multi-model anomaly detection system** for monitoring and logging environments. Modern systems generate massive volumes of operational data, including metrics related to CPU usage, memory consumption, response time, and network activity. Identifying abnormal patterns in these metrics is critical for **detecting system failures, performance degradation, security threats, and infrastructure anomalies**.

The project applies several **unsupervised machine learning algorithms** to detect anomalies in system monitoring data. Because anomalies are rare and often unlabeled, unsupervised models are ideal for discovering unusual behavior without prior classification.

The goal of this project is to demonstrate a **complete anomaly detection workflow**, including:

- Data preprocessing
- Feature scaling
- Multi-model anomaly detection
- Visualization of anomalies
- Feature-level anomaly analysis

This project is designed as a **portfolio project for data science and machine learning**, demonstrating practical anomaly detection techniques used in monitoring, cybersecurity, and financial fraud detection.

---

## Dataset

The dataset used in this project comes from Kaggle:

**Logging & Monitoring Anomalies Dataset**

It contains simulated monitoring metrics that resemble real operational logs from distributed systems.

### Dataset Characteristics

- **Rows:** 100,000
- **Columns:** 31
- **Data Type:** System monitoring metrics

### Example Variables

- CPU_Usage_Percent
- Memory_Usage_MB
- Network_Traffic
- Response_Time_ms
- Failed_Transactions
- Disk_IO

These variables allow anomaly detection models to identify unusual system behavior.

---

## Machine Learning Models Used

The project evaluates several **unsupervised anomaly detection algorithms**.

### 1. K-Means Clustering
K-Means groups observations into clusters based on similarity. Points that fall into smaller or distant clusters may represent anomalies.

**Purpose in this project:**
- Identify clusters of system behavior
- Detect unusual clusters

---

### 2. Isolation Forest
Isolation Forest isolates anomalies by randomly partitioning the feature space. Anomalies require fewer splits to isolate compared to normal observations.

**Advantages**
- Works well with high-dimensional data
- Efficient on large datasets

---

### 3. One-Class SVM
One-Class SVM learns the boundary of normal data and identifies observations that fall outside that boundary.

**Advantages**
- Good for novelty detection
- Effective in high-dimensional spaces

---

### 4. DBSCAN
DBSCAN is a density-based clustering algorithm that identifies anomalies as points that fall in **low-density regions**.

**Advantages**
- Detects clusters of arbitrary shape
- Identifies noise points

---

### 5. Local Outlier Factor (LOF)
LOF measures the **local density deviation** of each data point relative to its neighbors.

Points with significantly lower density compared to surrounding observations are flagged as anomalies.

---

## Project Workflow

The project follows a typical machine learning pipeline.

```
Load Dataset
      ↓
Data Cleaning
      ↓
Feature Selection (numeric variables)
      ↓
Feature Scaling
      ↓
Run Multiple Anomaly Detection Models
      ↓
Compare Model Results
      ↓
Visualize Outliers
      ↓
Analyze Feature-Level Anomalies
```

---

## Anomaly Detection Results

After running the models, the following number of anomalies were detected:

| Model | Anomalies Detected |
|------|------|
KMeans | 49,841 |
Isolation Forest | 5,000 |
One-Class SVM | 5,000 |
DBSCAN | 100,000 |
Local Outlier Factor | 5,000 |

Isolation Forest, SVM, and LOF were configured with **5% contamination**, resulting in approximately 5,000 anomalies.

---

## Visualizations

To better understand anomalies, several visualization techniques were used.

### PCA Projection
Principal Component Analysis reduces the dataset to two dimensions so anomalies can be visualized in a scatter plot.

### Feature Distribution Plots
Boxplots and histograms compare feature distributions between normal observations and anomalies.

### Feature Scatter Plots
Scatter plots reveal unusual relationships between variables.

Example:

- CPU Usage vs Memory Usage
- Network Traffic vs Response Time

### Time Series Anomaly Detection
Anomalies can also be visualized across time to detect system events or spikes in activity.

### Feature-Level Z-Score Heatmaps
Z-scores help identify **which variables contribute most to anomalies**.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

---

## Project Structure

```
anomaly-detection-project
│
├── data
│   └── logging_monitoring_anomalies.csv
│
├── notebooks
│   └── anomaly_analysis.ipynb
│
├── src
│   ├── anomaly_models.py
│   └── main.py
│
├── visualizations
│
└── README.md
```

---

## Key Insights

The analysis shows that several monitoring variables contribute to anomalies, including:

- High CPU usage
- Abnormal response times
- Spikes in network traffic
- Unusual memory consumption

Isolation Forest, LOF, and One-Class SVM produced consistent anomaly counts, suggesting that these models effectively captured unusual patterns in the monitoring data.

---

## Applications

This type of anomaly detection system can be used in:

- **IT infrastructure monitoring**
- **Cybersecurity threat detection**
- **Fraud detection**
- **Financial transaction monitoring**
- **Manufacturing quality control**

---

## Future Improvements

Possible extensions for this project include:

- Hyperparameter optimization for DBSCAN
- Real-time anomaly detection pipelines
- Streamlit dashboards for interactive monitoring
- Deep learning anomaly detection (Autoencoders)
- Model evaluation using labeled anomaly datasets

---

## Author

Data Science / Machine Learning Portfolio Project
