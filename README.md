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

### STEP 4: VISUALIZATION

## **1.Gender Distribution Bar Chart**

**counts the number of occurrences of each gender in dataset and creates a **vertical bar chart** to represent those counts.** **It is used for **exploratory data analysis (EDA)** to check for "class imbalance." Understanding the gender split helps determine if your customer segments will be skewed toward one group or if the mall attracts a balanced audience.**

### **Understanding the Output (The Plot)**
* **The X-Axis:** Displays the categories being compared (**Female** and **Male**).
* **The Y-Axis:** Represents the **Count** (the total number of customers in each category).
* **The Bars:** The height of each bar corresponds to the number of people.
    * **Female Bar:** You will notice this bar is higher (112), showing that women make up the majority of the sampled customers.
    * **Male Bar:** This bar is lower (88), showing fewer male customers in this specific dataset.
* **`plt.bar_label`:** This is the line that adds the exact numbers (**112** and **88**) directly on top of the bars, making the chart much easier to read at a glance without having to guess the values from the Y-axis.


  <img width="540" height="471" alt="image" src="https://github.com/user-attachments/assets/d2016dc9-0151-4dce-8f7e-f59e7d490a40" />


## **2.Age Distribution Histogram**

---

**The Matplotlib library to perform exploratory data analysis, specifically focusing on the demographic makeup of a customer base. Here is a brief explanation of why this approach was used and what the resulting image reveals:**

### Why Used
* **Data Summarization:** Instead of looking at a long list of individual ages, the code uses a **histogram** to group data into 20 "bins." This makes it easy to spot trends and patterns at a glance.
* **Visual Clarity:** The use of a specific purple color (`#9b59b6`) and black edges ensures the bars are visually distinct. Setting a large figure size (10x8) prevents the data from looking cramped.
* **Precision Labeling:** The `bar_label` function is the most important part of this code. It takes the guesswork out of reading the graph by placing the exact "frequency" (the number of people) directly above each bar.
* **Contextualization:** Adding titles and axis labels ensures that anyone looking at the chart immediately understands they are looking at **how many customers (Frequency)** fall into specific **age groups (Age)**.

---

### What the Output Shows 
The histogram reveals a **multi-modal distribution**, meaning there are several distinct "peaks" of customer activity across different life stages:

* **The Primary Peak (Ages 31–33):** This is your largest customer segment, with **22 people** falling into this narrow age range. It is closely supported by the 34–36 age group, which has **20 people**.
* **The Secondary Peak (Ages 47–49):** There is a significant "resurgence" in engagement among older adults, with **18 people** recorded in this bracket. This suggests the brand appeals to both Millennials and Gen X.
* **Young Adult Interest:** There is a strong starting point with **17 people** in the youngest bracket (roughly ages 18–20), indicating the brand is successful at capturing new, young customers.
* **The Mid-Life Dip:** There is a noticeable drop in frequency during the early 40s (only **5 people**) and a major "valley" in the mid-50s, where only **2 people** are recorded.
* **Retirement Consistency:** Engagement levels out toward the end of the spectrum, with a consistent group of **8 people** appearing in the 65–68 age range.


**In short:** The visualization proves that your business is most successful with people in their **early 30s**, but it also maintains a very strong secondary market among those in their **late 40s**.

  <img width="841" height="702" alt="image" src="https://github.com/user-attachments/assets/66932cbb-17ae-481c-8844-854fd29837a4" />

