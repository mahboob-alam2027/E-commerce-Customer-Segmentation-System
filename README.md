# E-commerce Customer Segmentation System

An unsupervised machine learning project that segments e-commerce customers into distinct groups based on their demographics, spending behavior, and engagement — enabling data-driven, targeted marketing strategies.

## Overview

Businesses often treat all customers the same way, missing opportunities to tailor offers, campaigns, and retention strategies. This project uses **clustering algorithms** to automatically discover natural customer segments in an e-commerce dataset, without any predefined labels. The resulting clusters reveal patterns such as high-value spenders, budget-conscious shoppers, and families with children — insights that can directly inform marketing and product decisions.

## Dataset

The dataset (`smartcart_customers.csv`) contains customer records with fields including:

- **Demographics**: Year of birth, education, marital status, income
- **Household**: Number of kids/teens at home
- **Purchase behavior**: Spending across product categories (wine, fruits, meat, fish, sweets, gold products)
- **Engagement**: Recency of last purchase, customer enrollment date, campaign response

## Project Workflow

### 1. Data Cleaning & Preprocessing
- Handled missing values in `Income` using median imputation
- Removed outliers (unrealistic ages and extreme income values)

### 2. Feature Engineering
- `Age` derived from birth year
- `Customer_Tenure_Days` calculated from enrollment date
- `Total_Spending` aggregated across all product categories
- `Total_Children` combined from kids and teens at home
- `Education` simplified into Undergraduate / Graduate / Postgraduate
- `Living_With` derived from marital status (Partner / Alone)

### 3. Exploratory Data Analysis
- Pairplots to visualize feature relationships and spot outliers
- Correlation heatmap to understand feature interdependencies

### 4. Encoding & Scaling
- One-hot encoding for categorical features (Education, Living_With)
- Standardization of all features using `StandardScaler`

### 5. Dimensionality Reduction
- Applied **PCA** (3 components) to reduce feature space and visualize customer distribution in 3D

### 6. Determining Optimal Clusters
- **Elbow Method** (WCSS + `KneeLocator`) to identify the optimal number of clusters
- **Silhouette Score** analysis to validate cluster quality
- Combined visualization comparing both metrics

### 7. Clustering
- **K-Means Clustering**
- **Agglomerative (Hierarchical) Clustering** with Ward linkage
- 3D visualization of resulting clusters in PCA space

### 8. Cluster Characterization
- Analyzed cluster sizes and distributions
- Compared clusters on income vs. spending
- Generated per-cluster feature summaries to profile each segment

## Tech Stack

- **Python**
- **Pandas / NumPy** — data manipulation
- **Matplotlib / Seaborn** — visualization
- **Scikit-learn** — preprocessing, PCA, KMeans, Agglomerative Clustering, Silhouette Score
- **Kneed** — automated elbow point detection

## Key Takeaways

- Customers can be grouped into meaningful segments purely from behavioral and demographic data, without labeled outcomes
- PCA helps visualize high-dimensional customer data in an interpretable way
- Combining the Elbow Method and Silhouette Score gives more confidence in choosing the right number of clusters
- Comparing multiple clustering algorithms (K-Means vs. Agglomerative) helps validate that discovered segments are robust, not artifacts of a single method

## How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/<your-username>/E-commerce-Customer-Segmentation-System.git
   cd E-commerce-Customer-Segmentation-System
   ```
2. Install dependencies
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn kneed
   ```
3. Open the notebook
   ```bash
   jupyter notebook E-commerce_Customer_Segmentation_System.ipynb
   ```

## Future Improvements

- Compute cluster profiles on raw (unscaled) features for easier business interpretation
- Add DBSCAN or Gaussian Mixture Models as additional clustering approaches
- Build an interactive dashboard to explore segments
- Translate clusters into actionable marketing personas

## Author

Feel free to connect or reach out with feedback and suggestions!
