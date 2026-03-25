<h1 align="center" style="font-family: 'Georgia', serif; font-size: 32px; font-weight: 700; margin: 20px 0 8px 0;">
🌐 Network Traffic <em>Data Analysis</em>
</h1>

<p align="center">
  <img src="https://www.secquest.co.uk/wp-content/uploads/2024/04/network-security-2048x1365.jpg" width="600" style="border-radius: 12px; box-shadow: 0 4px 16px rgba(0,0,0,0.15);"/>
</p>

<p align="center">
  A data analysis project to identify patterns in network traffic and prepare data for intrusion detection using Python.
</p>

---

## 📌 Overview

This project performs an end-to-end exploratory data analysis (EDA) on the **CICIDS (Canadian Institute for Cybersecurity Intrusion Detection System)** network traffic dataset. The dataset contains **288,602 records** and **79 features**, each representing a single network flow classified as either **Normal Traffic** (BENIGN) or **Attack** (malicious/infiltration).

The goal is to understand network flow properties, discover significant relationships among attributes, and pre-process the data to support future machine learning model training for intrusion detection.

---

## 🔍 What's Inside

| Section | Description |
|---|---|
| **1. Introduction** | Background on network security and project objectives |
| **2. Tools & Technology** | Libraries and environment used |
| **3. Dataset Description** | Overview of the CICIDS dataset and its features |
| **4. Data Understanding** | Analysis of the 16 selected key attributes |
| **5. Data Preparation** | Loading, filtering, cleaning, and transforming the data |
| **6. Data Analysis** | Summary statistics and correlation analysis |
| **7. Data Exploration** | Charts, visualizations, and hypothesis testing |
| **8. Summary** | Key findings and observations |
| **9. Conclusion** | Reflections and skills gained |

---

## 🛠️ Technologies Used

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Manipulation-green?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-teal)
![SciPy](https://img.shields.io/badge/SciPy-Hypothesis%20Testing-blueviolet?logo=scipy&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-blue?logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)

| Library | Purpose |
|---|---|
| **Python 3.11** | Core programming language |
| **Pandas** | Data loading, filtering, cleaning, and transformation |
| **Matplotlib** | Bar charts, pie charts, boxplots |
| **Seaborn** | Enhanced statistical visualizations |
| **SciPy** | Independent samples t-test for hypothesis testing |
| **NumPy** | Numerical computing backbone |
| **Jupyter Notebook** | Interactive development and documentation |

---

## 📊 Dataset

- **Source:** CICIDS Network Traffic Dataset — Canadian Institute for Cybersecurity, University of New Brunswick
- **Records:** 288,602 (filtered to 488,115 rows, then cleaned to 488,079 after removing missing values)
- **Features:** 79 (16 selected for analysis)
- **Target Variable:** `Label` → `Normal Traffic` (BENIGN) or `Attack` (Infiltration)

### Selected Features

| Feature | Type | Description |
|---|---|---|
| Destination Port | Flow-based | Target port number on destination machine |
| Flow Duration | Flow-based | Total duration of the network flow (microseconds) |
| Total Fwd Packets | Packet-based | Packets sent from source to destination |
| Total Backward Packets | Packet-based | Packets sent from destination to source |
| Fwd Packet Length Mean | Packet-based | Average forward packet size |
| Bwd Packet Length Mean | Packet-based | Average backward packet size |
| Flow Bytes/s | Flow-based | Bytes transferred per second |
| Flow Packets/s | Flow-based | Packets sent per second |
| Packet Length Mean | Packet-based | Mean packet length across all directions |
| Packet Length Std | Packet-based | Standard deviation of packet lengths |
| Average Packet Size | Packet-based | Mean size of all packets in the flow |
| Active Mean | Time-based | Average active time before becoming idle |
| Idle Mean | Time-based | Average idle time before becoming active |
| Label | Target | Normal Traffic or Attack |

---

## 🔬 Key Findings

- **Class Distribution:** 288,548 Normal Traffic vs 199,531 Attack records — moderate class imbalance present.
- **Missing Values:** 36 missing values found in `Flow Bytes/s` column — removed using `dropna()`.
- **Duplicate Records:** 139,389 duplicate records identified — significant data quality issue.
- **Top Correlated Features:**
  - Packet Length Mean & Average Packet Size: **0.9951** (near-redundant)
  - Total Backward Packets & Total Length of Bwd Packets: **0.9615**
  - Total Fwd Packets & Total Backward Packets: **0.9498**
- **Hypothesis Test (Flow Duration):** t-statistic = 0.716, p-value = 0.474 → **No significant difference** between Normal Traffic and Attack in mean Flow Duration.
- **Skewness & Kurtosis:** Both Flow Duration and Packet Length Mean showed high positive skewness and extreme kurtosis — heavy tails and many outliers present.

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/akisavujel/network-traffic-analysis.git
   cd network-traffic-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install pandas matplotlib seaborn scipy numpy jupyter
   ```

3. **Download the dataset**  
   Place the CICIDS dataset CSV file in the project directory.

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

5. **Run all cells**  
   Open the `.ipynb` file and run all cells sequentially.

---

## 📁 Project Structure

```
network-traffic-analysis/
│
├── network_traffic_analysis.ipynb   # Main Jupyter Notebook
├── pdf/                              # document on project 
└── README.md                        # Project documentation
```

---

## 👩‍💻 Author

**Akisha Bhujel**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akishabhujel/)
[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?logo=kaggle&logoColor=white)](https://www.kaggle.com/akisavujel)
[![Hashnode](https://img.shields.io/badge/Hashnode-2962FF?logo=hashnode&logoColor=white)](https://hashnode.com/@akisavujel)
[![Portfolio](https://img.shields.io/badge/Portfolio-green?logo=github&logoColor=white)](https://akisavujel.github.io/Portfolio/)

<p align="center">
  <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExZzUxMWs3YXU5OXgwYm4wdDJwanQ5aTMyOG1sa215cDN4Nml6aXJnbSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/L9Q2rzzBHrfv4a1y4h/giphy.gif" width="150" style="border-radius: 12px;"/>
</p>

---

<p align="center">
I love u cutu❤️
</p>
