# ⚽ Premier League Referee Bias: A Data-Driven Investigation

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/downloads/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Lab-orange.svg)](https://jupyter.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.2%2B-brightgreen.svg)](https://scikit-learn.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.10%2B-ff6f00.svg)](https://www.tensorflow.org/)

Have you ever watched a match and screamed at the TV, convinced the referee was biased against your team? Was it just passion, or was there something more to it? This project moves beyond speculation and uses a decade of Premier League data to answer the question: **Can we quantify and even predict referee bias?**

This repository contains an end-to-end machine learning project that scrapes, analyzes, and models 10 seasons of match data to uncover the subtle patterns of officiating.

## 🌟 Why It Matters

In the world of sports, integrity is everything. While outright corruption is rare, unconscious bias—favoring home teams, big clubs, or reacting to crowd pressure—can subtly influence the beautiful game. This project aims to:

* **Provide Objective Analysis:** Replace emotional debate with statistical evidence and machine learning models.
* **Showcase a Full-Stack ML Project:** Demonstrate a complete workflow from data acquisition and feature engineering to model training and interpretation.
* **Build an Analytical Tool:** Create a model that can flag matches with a high probability of biased officiating, serving as a powerful tool for sports analytics.

## 🛠️ Tech Stack

This project leverages a modern stack for data science and machine learning:

* **Data Collection:** `Python`, `Requests`, `BeautifulSoup4`
* **Data Manipulation & Analysis:** `Pandas`, `NumPy`, `SciPy` (for statistical tests)
* **Data Visualization:** `Matplotlib`, `Seaborn`
* **Machine Learning:** `Scikit-learn` (for clustering and preprocessing), `TensorFlow` (for the MLP classifier)
* **Environment:** `Jupyter Notebook` for iterative analysis and clear documentation.

## 🔬 How It Works: The Methodology

The project follows a rigorous multi-step approach to tackle this complex and label-scarce problem.

### 1.  automated Data Pipeline
An automated scraper was built to collect and parse 10 seasons of match data (2014-2024), resulting in a rich dataset of over 3,800 matches. The pipeline handles data cleaning, type conversion, and integration, creating a pristine dataset ready for analysis.

### 2. Statistical Validation
Before modeling, we had to confirm if bias indicators even exist. Key officiating metrics like fouls, card issuance, and stoppage time were analyzed. **Statistical tests (t-test, Wilcoxon signed-rank test)** were applied to validate that these metrics showed statistically significant differences in certain match conditions (e.g., home vs. away teams).

### 3. The Weak Supervision Challenge 💡
The biggest challenge? There's no "biased" or "not biased" label in the real world. To solve this, I innovated a **weak supervision** strategy to programmatically generate our training labels. This involved a dual-method approach:
* **Unsupervised Clustering (K-Means):** Grouping matches into clusters based on officiating metrics to find natural patterns of "strict" vs. "lenient" officiating.
* **Rule-Based Heuristics:** Applying domain knowledge to refine the cluster labels. For example, a cluster with an abnormally high foul count against the away team might be labeled as potentially "biased."

### 4. Modeling & Prediction
With our generated labels, a regularized **Multi-Layer Perceptron (MLP) classifier** was built using TensorFlow and Scikit-learn. The model was trained to identify potentially biased matches based on pre-match and in-game features.

## 📊 Key Findings & Results

The final model achieved an **80% accuracy** and a **0.85 AUC score**, demonstrating a strong ability to distinguish between matches it identifies as potentially biased and those it considers neutral.

This confirms that patterns of potentially biased officiating are not just random noise—they are detectable and can be modeled with a significant degree of accuracy. The model provides a quantitative tool to flag games that warrant closer scrutiny.

## 🚀 Getting Started

Want to run the analysis yourself?

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YufanPeter/Premier-League-Analysis-Referee-Bias-.git](https://github.com/YufanPeter/Premier-League-Analysis-Referee-Bias-.git)
    cd Premier-League-Analysis-Referee-Bias-
    ```

2.  **Install the dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Explore the notebooks:**
    The analysis is broken down into several Jupyter notebooks. Start with the data scraping and EDA notebook to follow the journey from raw data to final insights!
    * `Data Scraping.ipynb`
    * `Data Cleaning & Preprocessing.ipynb`
    * `Exploratory Data Analysis (EDA).ipynb`
    * `Modeling.ipynb`

---
