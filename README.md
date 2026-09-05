# Iranian Transactions - Data Cleaning & Exploratory Analysis

## 1. Project Overview

This project focuses on analyzing a deliberately corrupted, synthetic dataset of Iranian financial transactions. The primary goal is to demonstrate a complete data science workflow: from cleaning and standardizing messy data to performing exploratory data analysis (EDA) to uncover meaningful patterns.

The dataset is designed to mimic common real-world data quality issues, providing a practical challenge for practicing data cleaning, preprocessing, and analysis skills.

**Dataset Source:** [Dirty Iranian Transactions Dataset](https://www.kaggle.com/datasets/hosseinbadrnezhad/dirty-iranian-transactions-dataset) on Kaggle.

## 2. Objective

The analysis is divided into two main stages:

1.  **Data Quality & Cleaning:** Identify and rectify intentional inconsistencies, such as:
    *   Inconsistent categorical labels and spelling variations.
    *   Missing values.
    *   Erroneous or impossible values (e.g., negative transaction amounts, zero-value transactions on successes).

2.  **Exploratory Data Analysis (EDA):** After cleaning the data, we explore it to answer key business questions, including:
    *   Transaction volume by city and card type.
    *   Transaction success/failure patterns across different segments.
    *   Card preferences across various cities.
    *   Temporal transaction patterns (by time of day, day of week).
    *   Analysis of transaction amount distributions.

## 3. Dataset

The data used in this project is the `trx-10k.csv` file from the linked Kaggle dataset. It contains **10,000** synthetic transaction records with the following columns:
*   `status`: The outcome of the transaction (e.g., `success`, `fail`).
*   `time`: The date and time of the transaction.
*   `card_type`: The type of payment card used (e.g., `Visa`, `Mastercard`).
*   `city`: The city where the transaction originated.
*   `amount`: The transaction amount.
*   `id`: A unique transaction identifier.

## 4. Key Findings

### Geography
*   **Tehran** is the dominant city for transaction volume, accounting for the largest share.
*   **Tabriz** is the second-largest location by transaction count.

### Card Usage
*   **Visa** and **Discover** are the most frequently used card types.
*   There are observable variations in card type preferences across different cities.

### Transaction Outcomes
*   Success rates for transactions vary depending on the card type used.
*   It is important to distinguish between raw transaction counts and success rates when analyzing performance.

### Temporal Patterns
*   Transaction activity shows clear patterns throughout the day, with certain hours being busier than others.
*   The busiest times are typically in the late morning and early evening.

### Data Quality
*   The raw dataset contained a significant number of inconsistent labels and missing values.
*   A systematic cleaning process, including standardization and distribution-based imputation, was essential to make the data suitable for analysis.

## 5. Limitations

*   **Synthetic Data:** It is crucial to note that this dataset is **synthetically generated**. The patterns and insights derived from it should be interpreted as characteristics of the dataset itself and should **not** be used to make inferences about real-world Iranian financial behavior.
*   **Imputation Strategy:** The random categorical imputation used for missing values preserves the overall distribution of the data but does not account for complex relationships between different variables (e.g., the relationship between a city and the preferred card type used there).

## 6. Dependencies

This project relies on the following Python libraries:
*   **Python 3**
*   **[Pandas](https://pandas.pydata.org/):** For data manipulation and analysis.
*   **[NumPy](https://numpy.org/):** For numerical computing.
*   **[Matplotlib](https://matplotlib.org/) & [Seaborn](https://seaborn.pydata.org/):** For data visualization.

## 7. How to Run

## Requirements

* Python 3
* Pandas
* Matplotlib
* Jupyter Notebook
* ipykernal

## Running with `uv`

Clone the repository and navigate into it:

```bash
git clone <repository-url>
cd iranian-transactions-eda
```

Install the dependencies:

```bash
uv sync
```

## Running with `pip`

Create and activate a virtual environment:

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Linux/macOS:

```bash
source .venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter notebook
```

Open `Iranian_transactions_EDA.ipynb` and run the notebook

## Project Structure

```text
Iranian-transactions-EDA.ipynb/
├── data/
│   └── Iranian Transactions.csv
├── Iranian_transactions_EDA.ipynb
├── README.md
├── requirements.txt
├── pyproject.toml
├── .python-version
├── uv.lock
└── .gitignore
```