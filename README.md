# Customer Segmentation Using PCA and K-Means Clustering

## Project Overview

Customer segmentation is a crucial business strategy that helps organizations understand customer behavior and design targeted marketing campaigns. This project applies Principal Component Analysis (PCA) and K-Means Clustering to segment customers based on demographic and spending characteristics.

The objective is to identify distinct customer groups and generate meaningful customer personas that can support business decision-making and personalized marketing strategies.

---

## Problem Statement

Businesses often serve customers with different purchasing habits, income levels, and spending behaviors. Treating all customers the same may reduce marketing effectiveness and customer engagement.

The goal of this project is to:

- Reduce dataset dimensionality using PCA.
- Determine the optimal number of customer segments.
- Apply K-Means Clustering to identify distinct customer groups.
- Generate meaningful customer personas based on customer behavior.

---

## Dataset Information

### Dataset Name

Mall Customer Segmentation Dataset

### Features

| Feature | Description |
|----------|------------|
| CustomerID | Unique customer identifier |
| Genre | Gender of customer |
| Age | Customer age |
| Annual Income (k$) | Annual income in thousand dollars |
| Spending Score (1-100) | Spending score assigned by the mall |

### Dataset Summary

- Total Records: 200
- Total Features: 5
- Missing Values: 0
- Duplicate Records: 0

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Jupyter Notebook

---

# Project Workflow

## Step 1: Data Loading

The dataset was loaded using Pandas and inspected to understand its structure, dimensions, and feature types.

---

## Step 2: Data Quality Assessment

The dataset was checked for:

- Missing Values
- Duplicate Records

Results:

- Missing Values = 0
- Duplicate Records = 0

No data cleaning was required.

---

## Step 3: Feature Encoding

The categorical column **Genre** was converted into numerical format using Label Encoding.

---

## Step 4: Feature Selection

The **CustomerID** column was removed because it does not contribute to clustering.

---

## Step 5: Feature Scaling

StandardScaler was applied to standardize the dataset before PCA and clustering.

This ensures all features contribute equally to distance calculations.

---

## Step 6: Principal Component Analysis (PCA)

PCA was applied to reduce dimensionality from 4 features to 2 principal components.

### PCA Projection

PCA helped visualize customer distribution in a two-dimensional space while preserving most of the dataset's variance.

![PCA Projection](images/pca_projection.png)

---

## Step 7: Elbow Method

The Elbow Method was used to identify the optimal number of clusters by analyzing Within Cluster Sum of Squares (WCSS).

### Elbow Method Visualization

![Elbow Method](images/elbow_method.png)

Observation:

The elbow point appeared around **K = 5**, indicating five customer segments.

---

## Step 8: Silhouette Score Analysis

Silhouette Scores were calculated for different values of K to evaluate cluster quality.

### Silhouette Score Results

![Silhouette Scores](images/silhouette_scores.png)

### Scores Obtained

| K | Silhouette Score |
|---|---|
| 2 | 0.3153 |
| 3 | 0.3838 |
| 4 | 0.4123 |
| 5 | 0.4038 |
| 6 | 0.3888 |
| 7 | 0.3693 |
| 8 | 0.3602 |
| 9 | 0.3569 |
| 10 | 0.3594 |

Although K=4 achieved the highest Silhouette Score, K=5 was selected because it aligns with the Elbow Method and provides more meaningful customer segments.

---

## Step 9: K-Means Clustering

K-Means Clustering was applied using:

```python
n_clusters = 5
```

Each customer was assigned to one of five clusters.

---

## Step 10: Customer Segmentation Visualization

The final customer segments were visualized using PCA-transformed features.

### Customer Segmentation

![Customer Segmentation](images/customer_segmentation.png)

---

# Cluster Distribution

| Cluster | Number of Customers |
|----------|-------------------|
| 0 | 41 |
| 1 | 57 |
| 2 | 40 |
| 3 | 32 |
| 4 | 30 |

---

# Customer Personas

### Cluster 0 – Careful Customers

- High Income
- Low Spending Behavior
- Selective Buyers

### Cluster 1 – Budget Customers

- Moderate Income
- Low Spending Score
- Price Sensitive Customers

### Cluster 2 – Young Spenders

- Young Age Group
- Lower Income
- High Spending Tendencies

### Cluster 3 – Premium Customers

- High Income
- High Spending Score
- Most Valuable Customers

### Cluster 4 – Regular Customers

- Average Income
- Consistent Spending Behavior
- Stable Customer Segment

---

# Key Findings

- PCA successfully reduced the dataset to two dimensions for visualization.
- Elbow Method suggested five customer segments.
- Silhouette Score validated cluster quality.
- K-Means effectively separated customers into meaningful groups.
- Premium Customers and Young Spenders represent high-value marketing opportunities.
- Careful Customers may require targeted promotional strategies.

---

# Files Included

```text
Project3_Customer_Segmentation.ipynb
Mall_Customers.csv
Customer_Segmentation_Clustered.csv
README.md

images/
├── pca_projection.png
├── elbow_method.png
├── silhouette_scores.png
└── customer_segmentation.png
```

---
