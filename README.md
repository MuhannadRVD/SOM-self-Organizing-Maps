# 🧠 Credit Card Fraud Detection using Self-Organizing Map (SOM)

An unsupervised machine learning project that detects potential credit card fraud using a Self-Organizing Map (SOM) — a type of neural network that learns to cluster similar data points together without labeled fraud examples.

---

## 📌 Overview

Traditional fraud detection relies on labeled data (knowing which transactions are fraud). This project takes a different approach — it uses a **SOM to find anomalies** in credit card applications by identifying customers whose data behaves differently from the rest. These outliers are flagged as potential frauds.

---

## 🗂️ Dataset

- **File:** `Credit_Card_Applications.csv`
- **Features:** 15 input features per customer (financial and personal attributes)
- **Target column:** `Class` — whether the application was approved (used only for visualization, not training)

---

## ⚙️ How It Works

1. **Feature Scaling** — All features are scaled to [0, 1] using MinMaxScaler so the SOM trains evenly across all inputs.

2. **SOM Training** — A 10×10 SOM grid is trained on the data for 100 iterations. Each node in the grid learns to represent a cluster of similar customers.

3. **Visualization** — The SOM map is displayed using a color-coded grid:
   - **Lighter colors** = higher inter-neuron distance = more unusual customers
   - **Markers** show approved (green square) vs. rejected (red circle) applications

4. **Fraud Extraction** — The brightest nodes on the map (highest distance) are selected as suspicious clusters. Customers mapped to those nodes are extracted and inverse-transformed back to their original scale for review.

---

## 🔍 Results

The notebook outputs a table of customers flagged as potential frauds, showing their original (unscaled) feature values for manual review or further investigation.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| NumPy & Pandas | Data handling |
| Scikit-learn | Feature scaling |
| MiniSom | Self-Organizing Map implementation |
| Matplotlib / PyLab | Visualization |
| Google Colab | Development environment |

---

## 🚀 How to Run

1. Clone this repo and open `SOM.ipynb` in Google Colab
2. Upload `Credit_Card_Applications.csv` to the Colab session
3. Run all cells in order
4. The fraud list will be displayed at the end as an interactive table

```bash
# Install the required SOM library
pip install minisom
```

---

## 📁 Project Structure

```
├── SOM.ipynb                        # Main notebook
├── Credit_Card_Applications.csv     # Dataset
└── README.md                        # This file
```

---

## 💡 Key Concept

> This is **unsupervised** fraud detection — the model is never told which customers are fraudulent. It discovers suspicious patterns purely from the structure of the data itself.
