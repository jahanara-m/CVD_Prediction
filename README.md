# Cardiovascular Disease Prediction: CNN vs. LSTM
**A Comparative Study of Deep Learning Models for Clinical Analytics**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]
https://colab.research.google.com/github/jahanara-m/CVD_Prediction/blob/main/code.ipynb
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**TL;DR:** A controlled experiment comparing CNN and LSTM architectures for classifying cardiovascular disease from structured patient data. Key finding: The LSTM model, leveraging temporal patterns, achieved a superior average accuracy of 91.8% with efficient training.

---

##  Quick Results

| Model | Avg Accuracy | Avg Precision | Avg Recall | Avg F1-Score |
|-------|--------------|---------------|------------|--------------|
| CNN   | 89.0%        | 90.2%         | 87.6%      | 88.9%        |
| LSTM  | 91.8%        | 93.0%.        | 90.5%      | 91.6%        |

---

##  Key Insight

**Finding:** The LSTM model slightly outperformed the CNN, suggesting it is better at capturing sequential dependencies in patient data, even when the temporal ordering is not explicitly defined by dates. This aligns with clinical reasoning where patient state evolves over time. For structured tabular health data, an LSTM model with careful data preparation is the recommended starting point for classification tasks, providing strong performance without excessive complexity.

---

##  Analytical Workflow & Notebook Structure

The analysis follows a structured, reproducible pipeline in `code.ipynb`:

| Block |              Content.            |                                  Purpose                             |
|-------|----------------------------------|----------------------------------------------------------------------|
|   1   |       Setup & Configuration      |           Imports, defines `Config` class, sets random seeds         |
|   2   |    Data Loading & Exploration    |          Loads dataset, shows class distribution & preview           |
|   3   |    Data Preprocessing Pipeline   | Handles nulls, scales features, removes outliers, encodes categories |
|   4   |     Data Balancing with SMOTE    |                Applies SMOTE to handle class imbalance               |
|   5   |  CNN Model Definition & Training |              Defines 1D CNN architecture, runs 5-fold CV             |
|   6   | LSTM Model Definition & Training |               Defines LSTM with attention, runs 5-fold CV            |
|   7   |        Results Comparison        |            Aggregates metrics, generates comparison plots            |

---

##  How to Run & Reproduce

### **Option A: One-Click Live Demo (Recommended)**
The easiest way to review the full analysis is in Google Colab:
1.  Click the **[Open In Colab](https://colab.research.google.com/github/jahanara-m/CVD_Prediction/blob/main/code.ipynb)** badge above.
2.  In Colab, go to **Runtime > Run all** (`Ctrl+F9` / `Cmd+F9`).

### **Option B: Run Locally**
1.  **Clone** the repository:
    ```bash
    git clone https://github.com/jahanara-m/CVD_Prediction.git
    cd CVD_Prediction
    ```
2.  **Install** dependencies:
    ```bash
    pip install -r requirements.txt
    ```
    *The `Dataset.csv` file is included in this repository.*
3.  **Launch** Jupyter and open the notebook:
    ```bash
    jupyter notebook code.ipynb
    ```

---

##  Project Contents

**Root Files:**
- `code.ipynb` - Main analysis notebook
- `README.md` - This documentation
- `requirements.txt` - Python package dependencies  
- `Dataset.csv` - The labeled dataset for classification

---

##  Dependencies

Core Python packages are listed in `requirements.txt`. Main libraries include:
- `tensorflow`, `keras` (for deep learning models)
- `scikit-learn`, `imbalanced-learn` (for preprocessing and metrics)
- `pandas`, `numpy` (for data manipulation)
- `matplotlib` (for visualization)

---


##  License

This project is shared under the [MIT License](LICENSE). The `Dataset.csv` is provided for reproducibility of this specific analysis.
