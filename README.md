# Customer-Segmentation-Analysis
Segment customers based on behavior and demographics

## PROJECT GOAL: 
Gain experience in customer analytics, segmentation, and targeted insights

## DATASET & ITS SOURCE:

a)DOWNLOAD DATASET: - <a href ="https://github.com/priyanshu2003719/Customer-Segmentation-Analysis/blob/main/Mall_Customers.csv">DATASET</a>

b)The dataset Mall_Customers.csv contains basic information about 200 customers of a mall. It is commonly used for market basket analysis and customer segmentation using clustering techniques.
### **Column Overview**
* **CustomerID:** A unique identifier for each customer.
* **Gender:** The gender of the customer (Male or Female).
* **Age:** The age of the customer, ranging from **18 to 70 years** (average age is ~39).
* **Annual Income (k$):** The annual income of the customer in thousands of dollars, ranging from **$15k to $137k**.
* **Spending Score (1-100):** A score assigned by the mall based on the customer's spending behavior and nature, ranging from **1 to 99**.

The dataset has no missing values and consists of 4 numerical columns and 1 categorical column.

c) DATASERT SOURCE : - <a href ="https://github.com/TensorTitans01/customer-segmentation/blob/main/Mall_Customers.csv">DATASET SOURCE</a>

## PROJECT STEPS:

### STEP 1.  INSTALL LIBRARIES
Install several Python libraries at once using pip which is the standard package manager for Python.

### STEP 2:IMPORT LIBRARIES
###  The Libraries 
By listing them one after another, you are installing five of the most essential tools for data analysis and machine learning:

| Library | Purpose |
| :--- | :--- |
| **`pandas`** | Used for **data manipulation**. It allows you to load CSV files (like your Mall Customers data) and work with tables (DataFrames). |
| **`numpy`** | Short for "Numerical Python." It handles high-performance **mathematical operations** and multi-dimensional arrays. |
| **`matplotlib`** | A foundational library for creating **static visualizations** like line graphs, scatter plots, and histograms. |
| **`seaborn`** | Built on top of Matplotlib, it makes **statistical graphics** look more professional and easier to create (e.g., heatmaps or violin plots). |
| **`scikit-learn`** | The go-to library for **Machine Learning**. It contains algorithms for clustering (like K-Means), classification, and regression. |
| **`joblib`** | Used for **saving and loading** Python objects efficiently, specifically large NumPy arrays and trained machine learning models. |
---
### Working of libraries
1.  **Clean and explore** the data (`pandas`, `numpy`).
2.  **Visualize** customer clusters (`matplotlib`, `seaborn`).
3.  **Train a model**, such as a K-Means clustering algorithm, to segment your customers (`scikit-learn`).
4.  **Save your model** so you don't have to retrain it later (`joblib`).
   
### STEP 3 : LOADING & DESCRIPTION OF DATASET
This table explains each step of the Exploratory Data Analysis (EDA) process for the `Mall_Customers.csv` dataset. These commands help you understand the quality, structure, and distribution of your data before you start any modeling or clustering.

| Command Code | Purpose |
| :--- | :--- |
| **A) `pd.read_csv('Mall_Customers.csv')` & `customer_data.head()`** | Loads the dataset and displays the first 5 rows to preview the data. |
| **B) `customer_data.shape`** | Returns the number of rows and columns in the dataset. |
| **C) `customer_data.info()`** | Provides a summary of the dataset, including data types and non-null counts. |
| **D) `customer_data.isnull().sum()`** | Identifies the number of missing (null) values in each column. |
| **E) `customer_data.duplicated().sum()`** | Checks for and counts duplicate rows in the dataset. |
| **F) `customer_data.describe()`** | Generates descriptive statistics (mean, min, max, etc.) for numerical columns. |
| **G) `customer_data['Gender'].value_counts()`** | Counts the frequency of unique values in the 'Gender' column. |


