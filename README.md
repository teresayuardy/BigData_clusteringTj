# TransJakarta Passenger Segmentation Using K-Means Clustering

## Overview

This project explores passenger segmentation in TransJakarta using the K-Means clustering algorithm. Developed as part of a Big Data course project, the analysis aims to identify groups of passenger transactions based on travel time, age, and gender.

The results are explored further to understand how the identified clusters are distributed across TransJakarta corridors.

## Objectives

- Explore and prepare TransJakarta transaction data for analysis.
- Identify passenger transaction segments using K-Means clustering.
- Profile each cluster based on travel time, age, and gender.
- Examine the distribution of clusters across TransJakarta corridors.
- Visualize transaction patterns to support the interpretation of clustering results.

## Dataset

The dataset contains TransJakarta transaction records, including:

- Transaction ID
- Payment card information
- Passenger gender and birth year
- Corridor ID and corridor name
- Tap-in and tap-out stops
- Tap-in and tap-out timestamps
- Payment amount

**Dataset source:** [Add the original dataset source]

**Data period:** [Verify the date range of the complete dataset]

Note: The raw dataset may contain personal or transaction-level information. Sensitive fields should be excluded or anonymized before public sharing.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- K-Means Clustering
- MinMaxScaler

## Methodology

### 1. Data Preparation

- Inspected dataset columns, duplicate records, and missing values.
- Removed records with missing values in selected journey-related fields.
- Prepared the dataset for further analysis.

### 2. Feature Engineering

Three features were used for clustering:

- **Time:** Hour extracted from the tap-in timestamp.
- **Age:** Estimated age calculated from the passenger's birth year.
- **Gender:** Encoded as a numeric variable.

### 3. Feature Scaling

MinMaxScaler was applied to normalize the selected features before clustering.

### 4. K-Means Clustering

K-Means was configured with three clusters (`n_clusters=3`) and `random_state=42`.

### 5. Cluster Profiling and Visualization

The analysis examined average feature values for each cluster, compared transaction counts across corridors, and visualized tap-in time distributions using histograms and frequency polygons.

## Results & Findings

The notebook identifies three clusters with different average tap-in times and gender compositions:

- **Cluster 0:** Predominantly male-coded transactions with an average tap-in hour of approximately 06:56.
- **Cluster 1:** Predominantly female-coded transactions with an average tap-in hour of approximately 12:34.
- **Cluster 2:** Predominantly male-coded transactions with an average tap-in hour of approximately 17:50.

The analysis also compares corridor transaction counts across the three clusters to explore differences in corridor usage.

These clusters represent patterns in the selected transaction features and should not automatically be interpreted as confirmed occupations, commuting purposes, or round-trip behavior.

## Repository Structure

```text
BigData_clusteringTj/
├── Tj_dataset_clean.xlsx
├── Tj_dataset_raw.xlsx
├── eda_code.ipynb
├── final_paper.pdf
├── graphic_Cluster0.png
├── graphic_Cluster1.png
├── graphic_Cluster2.png
├── notes.txt
└── README.md
```

Additional files may be included if needed to support reproducibility.

## How to Run

1. Clone this repository.
2. Install the required Python libraries:

   `pip install pandas numpy matplotlib seaborn scikit-learn openpyxl jupyter`

3. Open `eda_code.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
4. Update the dataset file path in the notebook to match your local environment.
5. Run the notebook cells in order.

## Limitations

- The clustering uses only tap-in hour, estimated age, and encoded gender as input features.
- The number of clusters is set to three; further evaluation can help assess the suitability of this choice.
- The findings describe patterns in the available transaction data and do not independently establish passengers' occupations or travel purposes.

## Project Context

Academic project for a Big Data course, focusing on exploratory data analysis and unsupervised learning with K-Means clustering.
