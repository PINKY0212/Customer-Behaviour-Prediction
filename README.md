# Customer Personality Analysis with Python

## Overview
This project focuses on analyzing customer personality and behavior using a dataset from a marketing campaign. The goal is to segment customers into distinct clusters based on their income, seniority, and spending habits, and to explore associations between different customer attributes and their purchasing behaviors.

## Dataset
The dataset used is `marketing_campaign.csv`, which contains various customer attributes such as:
- Demographic information (Age, Education, Marital Status)
- Income and spending habits
- Purchase history across different product categories (Wines, Fruits, Meat, Fish, Sweets, Gold)
- Customer seniority (time since first purchase)

## Key Steps and Features

### 1. Data Preparation
- **Feature Engineering**:
  - Created new features like `Age`, `Spending` (total expenditure across categories), and `Seniority` (time as a customer).
  - Simplified categorical variables (e.g., grouped marital status into "Alone" or "In couple").
  - Added binary flags like `Has_child` and segmented `Children` into descriptive categories.
  
- **Outlier Handling**:
  - Removed missing values in the `Income` column.
  - Filtered out extreme income values (above 600,000).

### 2. Customer Segmentation
- **Clustering**:
  - Used Gaussian Mixture Model (GMM) to cluster customers into 4 segments:
    - Stars
    - Need attention
    - High potential
    - Leaky bucket
  - Visualized clusters in a 3D scatter plot using `plotly`, highlighting income, seniority, and spending.

### 3. Segmentation and Binning
- **Age, Income, and Seniority Groups**:
  - Binned continuous variables into meaningful segments (e.g., "Young," "Adult," "Mature," "Senior" for age).
  
- **Product Consumption Segments**:
  - Categorized spending on products (Wines, Fruits, etc.) into "Low consumer," "Frequent consumer," and "Biggest consumer," with a separate "Non consumer" category for zero spending.

### 4. Association Rule Mining
- **Market Basket Analysis**:
  - Used the Apriori algorithm to find frequent itemsets and association rules.
  - Focused on identifying patterns (e.g., what attributes are associated with being a "Biggest consumer" of wines).

## Tools and Libraries
- Python libraries: `numpy`, `pandas`, `matplotlib`, `seaborn`, `plotly`, `scikit-learn`, `mlxtend`.
- Key techniques: Standardization, normalization, clustering (GMM), association rule mining.

## How to Use
1. **Prerequisites**:
   - Install the required libraries: `pip install numpy pandas matplotlib seaborn plotly scikit-learn mlxtend dataprep`.
   - Download the dataset `marketing_campaign.csv` and place it in the same directory as the notebook.

2. **Run the Notebook**:
   - Execute the cells in the Jupyter notebook to perform data cleaning, clustering, visualization, and association rule mining.

3. **Explore Results**:
   - Analyze the cluster summaries and 3D visualizations.
   - Review the association rules to understand customer behavior patterns.

## Results
- **Cluster Insights**: The GMM clustering revealed distinct customer groups with varying income, seniority, and spending levels.
- **Association Rules**: Identified strong associations between customer attributes (e.g., income group, marital status) and product consumption segments.
