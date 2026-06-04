# SmartCart Customer Segmentation

## Overview
This project performs customer segmentation using data analysis, dimensionality reduction (PCA), and K-Means clustering. By analyzing customer demographics, purchasing behaviors, and marketing campaign responses, we identified four distinct customer profiles. These insights allow marketing teams to tailor their strategies, improve customer retention, and maximize profitability.

## Dataset
The dataset (`smartcart_customers.csv`) includes customer information such as:
- **Demographics:** Age, Education, Marital Status, Income, Number of Children.
- **Purchasing Behavior:** Spending amounts on Wines, Fruits, Meat, Fish, Sweets, and Gold products. 
- **Engagement:** Number of purchases made through various channels (Deals, Web, Catalog, Store), website visits, and responses to marketing campaigns.

## Data Preprocessing & Feature Engineering
To prepare the data for machine learning, the following steps were taken:
- **Missing Values:** Imputed missing `Income` values using the median.
- **Feature Engineering:** - `Age`: Calculated from `Year_Birth`.
  - `Customer_Tenure_Days`: Calculated the number of days since the customer joined.
  - `Total_Spending`: Aggregated spending across all product categories.
  - `Total_Children`: Combined the number of kids and teens at home.
  - `Living_With`: Grouped marital statuses into 'Partner' and 'Alone'.
  - `Education`: Simplified categories into 'Undergraduate', 'Graduate', and 'Postgraduate'.
- **Outlier Removal:** Filtered out extreme values (`Age` > 90 and `Income` > 600,000) to improve model robustness.
- **Redundant Features:** Dropped original columns that were replaced by engineered features to streamline the dataset.

## Machine Learning Pipeline
1. **Scaling:** Applied `StandardScaler` to ensure all features contributed equally to the model.
2. **Dimensionality Reduction:** Used Principal Component Analysis (PCA) to reduce the feature space to 3 components, retaining the most important variance while enabling 3D visualization.
3. **Clustering:** Deployed a `KMeans` clustering algorithm (`n_clusters=4`, `random_state=42`) to segment the customers.

## Customer Segments Identified
The model successfully grouped the customer base into four actionable segments:

### Cluster 0: Low-Income Young Families
- **Profile:** Low income and spending, with a high number of children.
- **Strategy:** Focus on discounts, essentials, and budget-friendly family deals.

### Cluster 1: High-Income Older Couples
- **Profile:** High income and high spending, with fewer children at home.
- **Strategy:** Target with premium products, personalized catalog offers, and loyalty rewards.

### Cluster 2: Premium High-Spending Singles (VIPs)
- **Profile:** Highest average income (~66k) and total spending (~1025). 100% live alone. They have the highest response rate to campaigns (~29.4%).
- **Strategy:** Offer VIP memberships, exclusive promotions, and early access to new products. This is the most valuable segment.

### Cluster 3: Family-Oriented Moderate Spenders
- **Profile:** Families with multiple children (~2.1 on average). Moderate income (~44k) and spending, but highly responsive to web marketing and visits (~7.0 visits/month).
- **Strategy:** Market family bundles, seasonal promotions, and value packs.

## Dependencies
To run this project locally, ensure you have the following Python libraries installed:
- `pandas`
- `scikit-learn`
- `seaborn`
- `matplotlib`

## How to Run
1. Clone this repository to your local machine.
2. Ensure `smartcart_customers.csv` is located in the same directory as the notebook.
3. Run the Jupyter Notebook `SmartCart.ipynb` to view the data processing, model training, and 3D cluster visualizations.

## Author
**Mohammed Akmal** Let's connect on [[LinkedIn]([url](https://www.linkedin.com/in/mohammed-akmal-8b00ba322/))](#)!
