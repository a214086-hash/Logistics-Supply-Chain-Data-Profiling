# Logistics and Supply Chain Data Profiling

## Assignment Information

- **Course:** TTTC3213 Data Engineering
- **Assignment:** Assignment 1 – Data Profiling (EDA) Report
- **Domain:** Logistics / Supply Chain
- **Dataset:** DataCo Smart Supply Chain
- **Programming Language:** Python 3.14.2
- **Development Environment:** GitHub Codespaces and Jupyter Notebook

## Team Members

| Name | Matric Number |
|---|---|
| LI HUA | A214086 |
| SONG SHIHONG | A207394 |
| CHU XINRAN | A214107 |
| LI HUA | A214086 |
| LI HUA | A214086 |
| LI HUA | A214086 |

## 1. Scenario

A regional e-commerce logistics company wants to assess the quality of its order and shipment records before using them to investigate shipping delays. The dataset is suitable because it contains shipping durations, delivery statuses, geographical information, missing values, and potential privacy risks. This assessment aims to identify data quality problems and determine whether the records are sufficiently reliable for future analysis of shipping reliability across regions and shipping modes.

## 2. Data Source

**Dataset:** DataCo Smart Supply Chain for Big Data Analysis

**Kaggle Dataset:** https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

**Original Source:** https://data.mendeley.com/datasets/8gx2fvg2k6/5

**Data Acquisition Method:**

The dataset was downloaded from Kaggle in CSV format and uploaded to GitHub Codespaces for analysis using Python and Pandas.

The dataset contains approximately 180,519 records and 53 columns, including order information, shipping durations, delivery statuses, geographical attributes, customer-related fields, and financial information.

The original and cleaned CSV files are excluded from this repository because of their size and privacy considerations.

## 3. Project Structure

```text
Logistics-Supply-Chain-Data-Profiling/
│
├── data/
│   ├── README.md
│   ├── DataCoSupplyChainDataset.csv
│   └── dataco_cleaned.csv
│
├── notebooks/
│   └── data_profiling.ipynb
│
├── .gitignore
├── README.md
└── requirements.txt
```

**Note:** The CSV files are stored locally in Codespaces and are not tracked by Git.

## 4. Data Profiling Objectives

This assignment focuses on diagnosing and handling data quality issues rather than building predictive models or dashboards.

The objectives are:

1. Identify missing values and justify the selected handling methods.
2. Detect potential outliers using the Interquartile Range (IQR) method.
3. Examine duplicate records, incorrect data types, inconsistent categorical formats, and invalid values.
4. Create diagnostic visualizations that expose data quality problems.
5. Identify personally identifiable information (PII) and potential sampling bias.
6. Evaluate the suitability and limitations of the dataset for logistics analysis.

## 5. Data Profiling Methods

### 5.1 Missing Values

Missing values are identified using Pandas `isna()` and summarized using counts and percentages.

Columns containing entirely missing values are removed because they provide no usable information. Remaining missing values are retained for further investigation when automatic imputation cannot be justified.

### 5.2 Outlier Detection

The Interquartile Range (IQR) method is used to identify potential outliers in the `Benefit per order` feature.

Potential outliers are flagged rather than automatically removed because unusually high profits or large losses may represent genuine business transactions.

### 5.3 Other Data Quality Issues

The following issues are examined:

- Exact duplicate records
- Repeated order and order-item identifiers
- Incorrect date formats and data types
- Inconsistent categorical formats
- Negative or invalid shipping durations
- Invalid order-item quantities
- Inconsistent order and shipping timestamps

### 5.4 Diagnostic Visualizations

The Jupyter Notebook includes four diagnostic visualizations:

1. Missing Values by Column
2. Outlier Detection: Benefit per Order
3. Shipping Mode Distribution
4. Top 10 Order Regions by Record Count

These charts help identify missing data, unusual numerical values, and potential group imbalance.

### 5.5 PII and Bias Risks

Potentially sensitive fields, including customer names, addresses, identifiers, and geographical coordinates, are identified and excluded from the cleaned analytical dataset when unnecessary.

Regional and shipping-mode distributions are examined to identify potential sampling imbalance.

## 6. Tools and Technologies

- Python 3.14.2
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- GitHub Codespaces
- Git and GitHub

## 7. How to Run

### Step 1: Open GitHub Codespaces

Open this repository on GitHub.

Click **Code → Codespaces → Create codespace on main**.

### Step 2: Prepare Python Environment

Create a virtual environment using Python 3.14:

```bash
python3.14 -m venv .venv
```

Activate the environment:

```bash
source .venv/bin/activate
```

### Step 3: Install Dependencies

Run the following command from the project root:

```bash
python -m pip install -r requirements.txt
```

### Step 4: Download the Dataset

Download the DataCo Smart Supply Chain dataset from Kaggle:

https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

Extract the downloaded archive and place `DataCoSupplyChainDataset.csv` inside the `data/` directory.

### Step 5: Open Jupyter Notebook

Open:

`notebooks/data_profiling.ipynb`

Select the **Python (Logistics EDA)** kernel.

### Step 6: Run All Cells

Select **Restart Kernel and Run All Cells**.

The notebook will:

1. Load the original dataset.
2. Perform initial data profiling.
3. Identify and handle missing values.
4. Detect and flag potential outliers.
5. Examine other data quality issues.
6. Generate diagnostic charts.
7. Assess PII and bias risks.
8. Validate the cleaned dataset.
9. Save the cleaned dataset locally as `data/dataco_cleaned.csv`.

## 8. Expected Outputs

The notebook generates:

- Dataset structure and descriptive statistics
- Missing-value counts and percentages
- IQR outlier detection results
- Duplicate-record and invalid-value checks
- Diagnostic visualizations
- PII and bias assessment
- Data quality summary before and after cleaning
- Cleaned CSV dataset

## 9. Limitations

- Statistical outliers may represent genuine business transactions and require further investigation.
- Flagged invalid records are not automatically corrected without supporting evidence.
- The dataset may contain unequal representation across regions and shipping modes.
- The absence of independently verified final delivery timestamps limits the assessment of actual delivery delays.
- Removing unnecessary personal information reduces privacy risks but does not guarantee complete anonymization.

## 10. Conclusion

This project evaluates the quality of logistics and supply chain records using systematic data profiling and documented cleaning decisions.

The assessment provides a basis for determining whether the dataset is suitable for future analysis of shipping reliability. Remaining data quality issues and sampling limitations must be considered before drawing operational conclusions.