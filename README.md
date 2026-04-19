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



| Command Code | Purpose | Result for this Dataset |
| :--- | :--- | :--- |
| **A) `pd.read_csv(...)` & `.head()`** | **Loading & Previewing:** Reads the file into a table (DataFrame) and displays the first 5 rows to check the column headers and data format. | Loads the data and shows columns like `CustomerID`, `Gender`, `Age`, `Annual Income`, and `Spending Score`. |
| **B) `customer_data.shape`** | **Dimensions:** Returns the "shape" of the dataset in terms of (Rows, Columns). | **(200, 5)**: This tells us there are 200 customers and 5 different attributes for each. |
| **C) `customer_data.info()`** | **Data Metadata:** Shows the data types (e.g., integer, object), the number of non-null entries, and memory usage. | Confirms that most columns are integers, except for `Gender` (object/string). |
| **D) `customer_data.isnull().sum()`** | **Missing Value Check:** Calculates the sum of null (empty) cells for every column. | All columns returned **0**, meaning the dataset is clean with no missing information. |
| **E) `customer_data.duplicated().sum()`** | **Duplicate Check:** Counts how many rows are exact copies of another row. | Returns **0**, confirming that every customer entry in the list is unique. |
| **F) `customer_data.describe()`** | **Statistical Summary:** Provides the mean, standard deviation, minimum, maximum, and quartiles for numerical columns. | Shows that the average customer is **39 years old** and the average income is **$60.56k**. 
| **G) `customer_data['Gender'].value_counts()`** | **Category Distribution:** Counts how many times each unique value (Male/Female) appears in the Gender column. | Reveals the gender balance (e.g., 112 Females and 88 Males) to see if the data is biased toward one group. |


