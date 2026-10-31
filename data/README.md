# Dataset Instructions

## Dataset Information

- **Dataset Name:** DataCo Smart Supply Chain for Big Data Analysis
- **Domain:** Logistics / Supply Chain
- **Format:** CSV
- **Source:** Kaggle

**Dataset URL:** https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

**Original Source:** https://data.mendeley.com/datasets/8gx2fvg2k6/5

## Download Instructions

1. Open the Kaggle dataset URL.
2. Sign in to Kaggle if required.
3. Download the dataset archive.
4. Extract the downloaded ZIP file.
5. Locate `DataCoSupplyChainDataset.csv`.
6. Place the CSV file inside this `data/` directory.

## Expected Directory Structure

```text
data/
├── README.md
├── DataCoSupplyChainDataset.csv
└── dataco_cleaned.csv
```

**Note:** `dataco_cleaned.csv` is generated automatically after successfully running the Jupyter Notebook.

## Dataset Description

The dataset contains approximately 180,519 records and 53 columns covering:

- Customer-related information
- Orders and order items
- Shipping durations
- Delivery statuses
- Shipping modes
- Geographic regions
- Sales and profit information

## Data Privacy

The original dataset contains customer-related information that may present privacy risks.

For this reason, the original and cleaned CSV files are excluded from Git tracking through `.gitignore`.

Only the Jupyter Notebook, project documentation, and dependency information are intended to be committed to GitHub.

## Usage

After downloading and placing the original CSV file in this directory, open:

`notebooks/data_profiling.ipynb`

Select the **Python (Logistics EDA)** kernel and run all notebook cells.

The cleaned dataset will be saved locally as:

`data/dataco_cleaned.csv`