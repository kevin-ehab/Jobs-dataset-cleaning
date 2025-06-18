# 🧹Jobs-dataset-cleaning

This project focuses on cleaning and preprocessing a dataset of job listings to prepare it for analysis. The original dataset had inconsistencies, missing values, and non-uniform formatting, all of which were addressed in this notebook.

## 📁 Dataset

- **Input**: `Uncleaned_DS_jobs.csv`
- **Output**: Cleaned DataFrame (in-memory)

## 📌 Cleaning Steps

### 1. 🧼 General Cleanup
- Loaded dataset using **Pandas**.
- Removed rows with invalid or placeholder values (`-1`) in important columns:
  - `Type of ownership`
  - `Revenue`
  - `Founded`
  - All columns containing `-1` values

### 2. 🗑 Column Management
- Dropped the `Competitors` column as it was sparse and not helpful.
- Removed rows where `Location` was "Remote" if they were outliers.

### 3. 🏢 Company Name Cleanup
- Cleaned `Company Name` column by removing job rating suffixes like `\n3.1`.

### 4. 💸 Salary Estimate Cleanup
- Removed `(Glassdoor est.)` text from `Salary Estimate`.
- Removed currency symbols (`$`) and replaced "K" with "000".
- Split the salary into two new columns:
  - `Lowest Salary`
  - `Highest Salary`

### 5. 💰 Revenue Column Formatting
- Cleaned `Revenue` column by removing unnecessary spaces for consistency.

## 🔧 Libraries Used

- `pandas`
- `numpy`

## 📊 Result

The cleaned dataset is now more consistent and suitable for further analysis, visualization, or modeling.
