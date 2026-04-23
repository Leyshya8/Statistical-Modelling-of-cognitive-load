# 🧠 Cognitive Load Classification — Subject-Independent Task Prediction

Classifying cognitive workload levels using physiological and behavioral features through machine learning.

This project implements a machine learning pipeline to predict the difficulty level of a task (Easy, Control, or Difficult) based on cognitive metrics. It utilizes a **Random Forest Classifier** and emphasizes robust evaluation using **Leave-One-Subject-Out (LOSO) Cross-Validation** to ensure the model generalizes across different individuals rather than just memorizing specific participants.

## 📋 Table of Contents
* [Features](#-features)
* [Tech Stack](#-tech-stack)
* [Prerequisites](#-prerequisites)
* [Installation](#-installation)
* [Usage](#-usage)
* [Analysis Pipeline](#-analysis-pipeline)
* [Project Structure](#-project-structure)
* [Contributing](#-contributing)
* [License](#-license)

## ✨ Features
* **Subject-Independent Validation** — Uses Leave-One-Subject-Out (LOSO) cross-validation to test the model's ability to predict data for a person it has never seen before.
* **Multi-Class Classification** — Categorizes cognitive load into three distinct levels: Low (EASY), Medium (CONTROL), and High (DIFF).
* **Feature Importance Ranking** — Identifies which metrics (such as `pcpd`, `msrt`, or `tlx`) are most predictive of cognitive workload.
* **Comprehensive Metrics** — Evaluates performance using Macro F1-Score, Weighted F1-Score, and a detailed Confusion Matrix.
* **Data Scaling** — Implements standard scaling to normalize feature distributions for improved model stability.

## 🛠 Tech Stack
| Component | Library / Tool |
| :--- | :--- |
| **Language** | Python 3.x |
| **Data Processing** | Pandas, NumPy |
| **Machine Learning** | Scikit-learn (RandomForest, LOSO) |
| **Visualization** | Seaborn, Matplotlib |

## ✅ Prerequisites
Ensure the following are installed:
* Python 3.10+
* The dataset file: `pone.0203629.s002.csv`

## 🚀 Installation

```bash
# 1. Clone the repository
git clone https://github.com/YourUsername/Cognitive-Load-Analysis.git
cd Cognitive-Load-Analysis

# 2. (Recommended) Create a virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn
```

## ▶️ Usage
Run the analysis script directly:
```bash
python cognitive_project.py
```
The script will output the data shapes, start the LOSO training process, and finally display the performance report and feature importance plots.

## 🔬 Analysis Pipeline
1. **Preprocessing**: Maps categorical task types to numeric targets and scales the 9 primary feature columns (`pcpd`, `bpcpd`, `msrt`, etc.).
2. **LOSO Cross-Validation**: Iteratively trains the model by leaving out one subject's data for testing in each fold to ensure subject-independence.
3. **Random Forest Training**: Employs 300 estimators with a maximum depth of 8 and balanced class weights to handle potential dataset imbalances.
4. **Visualization**: Generates a heatmap of the Confusion Matrix and a bar plot of Feature Importances.

## 📁 Project Structure
```text
Cognitive-Load-Project/
├── pone.0203629.s002.csv   # Dataset containing subject metrics and task types
├── cognitive_project.py    # Main script for training and evaluation
└── README.md               # Project documentation
```

## 🤝 Contributing
Contributions are welcome!
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/improvement`
3. Commit your changes: `git commit -m "Improve model accuracy"`
4. Push to the branch: `git push origin feature/improvement`
5. Open a Pull Request

## 📄 License
This project is licensed under the **MIT License** — see the LICENSE file for details.
