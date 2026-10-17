# ⚽ Football Expected Goals (xG) Prediction Model

## 📌 Project Overview

This project develops a machine learning model to predict **Expected Goals (xG)** in football using shot data from StatsBomb Open Data. It analyses shot characteristics and passing context to estimate the probability of a shot resulting in a goal.

The project uses Logistic Regression and XGBoost, comparing their predictions against StatsBomb's existing xG estimates. The objective is to explore how machine learning can support football performance analysis through data-driven insights.

## 🎯 Objectives

* Analyse football shot data from international tournaments.
* Perform data cleaning and exploratory data analysis (EDA).
* Engineer features such as shot distance, shooting angle, and shot type.
* Build an xG prediction model using Logistic Regression and XGBoost.
* Evaluate model performance using multiple classification metrics.
* Compare custom model predictions with StatsBomb's xG estimates.
* Visualise shot patterns and scoring probabilities.

## 📊 Dataset

The project uses **StatsBomb Open Data**, containing football match events, shot information, and related passing context.

### Tournaments Included

* 2018 FIFA World Cup
* UEFA Euro 2020
* Copa América 2024
* UEFA Euro 2024
* 2022 FIFA World Cup

The combined dataset contains 6,619 shots before cleaning and 6,347 shots after cleaning.

**Data source:** [StatsBomb Open Data on GitHub](https://github.com/statsbomb/open-data)

## 🛠️ Technologies Used

* **Python** – Data processing and model development
* **Pandas & NumPy** – Data manipulation and feature engineering
* **Matplotlib** – Data visualisation
* **Scikit-learn** – Model training and evaluation
* **XGBoost** – Gradient-boosted tree model
* **StatsBombPy** – Accessing StatsBomb event data
* **Jupyter Notebook** – Development and experimentation

## ⚙️ Project Workflow

### 1. Data Collection

Collected shot-event data from multiple international football tournaments using StatsBomb Open Data.

### 2. Data Cleaning

Removed penalty shots and penalty shootout attempts to focus the analysis on shots taken during regular match play and extra time.

### 3. Exploratory Data Analysis

Investigated relationships between shot distance, shooting angle, and goal outcomes using statistical summaries and visualisations.

### 4. Feature Engineering

Created features including:

* Shot distance
* Shooting angle
* Header indicator
* Key-pass indicator
* Cross, through-ball, cutback, and switch indicators
* Key-pass length
* Pass height and pass type indicators

### 5. Model Development

Developed two machine learning models:

* **Logistic Regression:** Baseline model for estimating goal probabilities.
* **XGBoost:** Gradient-boosted tree model incorporating shot characteristics and passing context.

### 6. Model Evaluation

Evaluated predictions using:

* **Log Loss:** Measures the quality of predicted probabilities.
* **Brier Score:** Measures the squared error of probabilistic predictions.
* **ROC-AUC:** Measures the model's ability to distinguish goals from non-goals.

### 7. Model Comparison

Compared the custom models against StatsBomb's existing xG estimates using the held-out 2022 FIFA World Cup dataset.

## 📈 Key Results

| Model               | Log Loss | Brier Score | ROC-AUC |
| ------------------- | -------: | ----------: | ------: |
| Logistic Regression |   0.2896 |           — |  0.7796 |
| XGBoost             |   0.2859 |      0.0823 |  0.7831 |
| StatsBomb xG        |   0.2665 |      0.0762 |  0.8148 |

*Metrics are from the notebook's reported evaluation results. Dashes indicate values not included in the results summarised here.*

The evaluation shows that XGBoost slightly improved upon the Logistic Regression baseline, while StatsBomb's xG estimates performed better across all three reported metrics.

The project demonstrates the importance of feature engineering, probability calibration, and reliable evaluation when developing football analytics models.

## 📂 Repository Structure

```text
football-xg-prediction/
│
├── xG_model(world_cup_2022).ipynb
├── README.md
└── requirements.txt
```

*The repository structure above is a suggested layout. Adjust the filenames to match your actual repository.*

## 🚀 How to Run the Project

### Prerequisites

Install Python 3.10 or a compatible version, along with Jupyter Notebook.

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <your-repository-folder>
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib scikit-learn xgboost statsbombpy mplsoccer
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `xG_model(world_cup_2022).ipynb` and execute the notebook cells in order.

**Note:** The notebook retrieves data from StatsBomb Open Data, so an internet connection is required for data collection.

## 🔮 Future Improvements

* Incorporate goalkeeper and defender positions from shot freeze-frame data.
* Explore additional contextual features, including defensive pressure and shot technique.
* Apply cross-validation across tournaments to assess generalisation.
* Tune hyperparameters systematically.
* Investigate calibration methods to improve probability estimates.
* Develop interactive dashboards to explore shot locations and xG predictions.
* Extend the model to league football and club-level performance analysis.

## 🏁 Conclusion

This project explores how machine learning can estimate goal-scoring probabilities using football event data. By combining shot characteristics, passing context, model evaluation, and visualisation, it provides a foundation for further work in football analytics and performance analysis.

The project is part of my ongoing exploration of **data science and football analytics**, with the long-term goal of applying analytical methods to real-world football performance.

## 📚 Acknowledgements

* [StatsBomb Open Data](https://github.com/statsbomb/open-data) for providing football event data.
* The open-source Python and machine learning communities for the tools used in this project.
