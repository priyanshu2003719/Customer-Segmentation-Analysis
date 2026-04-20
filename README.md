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

## **1. Gender Distribution Bar Chart**

 **The Matplotlib and **Pandas** libraries is used to create a categorical analysis of a customer database. By shifting from raw text data to a visual bar chart, it allows for an immediate understanding of the brand's gender demographics.**

### Why  Used
* **Categorical Comparison:** While a histogram (like your previous age chart) is for numbers, a **bar chart** is the best tool for comparing distinct categories like "Male" and "Female."
* **Data Aggregation:** The code uses `value_counts()` to automatically tally how many times each gender appears in the spreadsheet, saving the user from manual counting.
* **Visual Distinction:** High-contrast colors (Blue for Female, Red for Male) are used to make the categories instantly recognizable without even reading the labels.
* **Data Integrity:** By adding `bar_label`, the code ensures the exact headcounts are displayed, preventing any misinterpretation of the bar heights.


### What the Output Shows 
The resulting bar chart provides a clear snapshot of the customer base's gender split:

* **Primary Segment (Female):** The "Female" category represents the majority of the customer base. The chart shows an exact count of **112 female customers**.
* **Secondary Segment (Male):** The "Male" category represents the minority group in this dataset, with an exact count of **88 male customers**.
* **Total Sample Size:** By looking at the labels, we can determine that the total dataset consists of **200 customers** ($112 + 88$).
* **Gender Gap:** The visualization highlights a moderate gender gap; there are **24 more female customers** than male customers, suggesting the brand or product currently has a stronger appeal to women.
* **Proportional Insight:** Visually, females make up **56%** of the customer base, while males make up **44%**.

**In short:** This visualization proves that your customer base is predominantly female, providing a clear target for marketing strategies or product development.

<img width="540" height="471" alt="image" src="https://github.com/user-attachments/assets/d2016dc9-0151-4dce-8f7e-f59e7d490a40" />


## **2. Age Distribution Histogram**

**The Matplotlib library is used to perform exploratory data analysis, specifically focusing on the demographic makeup of a customer base. Here is a brief explanation of why this approach was used and what the resulting image reveals:**

### Why Used
* **Data Summarization:** Instead of looking at a long list of individual ages, the code uses a **histogram** to group data into 20 "bins." This makes it easy to spot trends and patterns at a glance.
* **Visual Clarity:** The use of a specific purple color (`#9b59b6`) and black edges ensures the bars are visually distinct. Setting a large figure size (10x8) prevents the data from looking cramped.
* **Precision Labeling:** The `bar_label` function is the most important part of this code. It takes the guesswork out of reading the graph by placing the exact "frequency" (the number of people) directly above each bar.
* **Contextualization:** Adding titles and axis labels ensures that anyone looking at the chart immediately understands they are looking at **how many customers (Frequency)** fall into specific **age groups (Age)**.

### What the Output Shows 
The histogram reveals a **multi-modal distribution**, meaning there are several distinct "peaks" of customer activity across different life stages:

* **The Primary Peak (Ages 31–33):** This is your largest customer segment, with **22 people** falling into this narrow age range. It is closely supported by the 34–36 age group, which has **20 people**.
* **The Secondary Peak (Ages 47–49):** There is a significant "resurgence" in engagement among older adults, with **18 people** recorded in this bracket. This suggests the brand appeals to both Millennials and Gen X.
* **Young Adult Interest:** There is a strong starting point with **17 people** in the youngest bracket (roughly ages 18–20), indicating the brand is successful at capturing new, young customers.
* **The Mid-Life Dip:** There is a noticeable drop in frequency during the early 40s (only **5 people**) and a major "valley" in the mid-50s, where only **2 people** are recorded.
* **Retirement Consistency:** Engagement levels out toward the end of the spectrum, with a consistent group of **8 people** appearing in the 65–68 age range.

**In short:** The visualization proves that your business is most successful with people in their **early 30s**, but it also maintains a very strong secondary market among those in their **late 40s**.

<img width="841" height="702" alt="image" src="https://github.com/user-attachments/assets/66932cbb-17ae-481c-8844-854fd29837a4" />


## **3. Annual Income Distribution Pie Chart**

**This code transitions from raw numerical data to a high-level socioeconomic profile of the customer base using **Pandas** and **Matplotlib**.**

### Why  Used
* **Data Categorization:** The `pd.cut` function is used to simplify complex financial data. Instead of looking at dozens of individual salary figures, it groups them into three meaningful buckets: **Low**, **Medium**, and **High** income.
* **Proportional Analysis:** A **pie chart** is chosen because it is the most effective way to visualize "parts of a whole." It allows you to see the market share each income group holds within your business.
* **Automated Calculation:** The `autopct` feature automatically calculates percentages so you don't have to perform manual math to understand the ratios.
* **Visual Strategy:** Specific colors are used to differentiate tiers, and a large figure size (10x8) ensures the labels remain readable and professional.

### What the Output Shows 
The resulting pie chart provides a clear breakdown of the purchasing power within your customer base:

* **Dominant Market (Medium Income):** More than half of your customers—**56.0%**—fall into the "Medium" income bracket ($40k – $80k). This suggests your product or service is most popular with middle-class earners.
* **Budget Segment (Low Income):** A significant quarter of your audience (**25.0%**) is in the "Low" income category (under $40k). This indicates your brand is still accessible or appealing to entry-level earners or students.
* **Luxury Segment (High Income):** The smallest portion of your audience, at **19.0%**, consists of "High" income earners (above $80k).
* **Economic Profile:** The chart reveals a healthy, "stable" business model where the majority of revenue comes from a broad middle-market rather than relying solely on a small group of wealthy individuals.

**In short:** This visualization proves that your brand is a **"mass-market" hit**, with its strongest foothold in the middle-income demographic while maintaining a healthy 25% reach into the budget-conscious segment.

<img width="636" height="659" alt="image" src="https://github.com/user-attachments/assets/16a50418-6df8-47fb-a963-761cbdc73454" />

## **4. Spending Score Distribution Horizontal Bar Chart**

**This performs a behavioral analysis of a customer base by visualizing "Spending Scores"—a metric typically used in retail to measure how much a customer spends relative to others.**

### Why Used
* **Ranking & Prioritization:** A **horizontal bar chart** (`barh`) is used here because it is the most effective way to display a list from highest to lowest. It allows the viewer to instantly see which spending behaviors are most dominant.
* **Custom Binning:** Instead of plotting every individual score, the data is manually grouped into logical ranges (e.g., 0-4, 5-9). This turns granular, noisy data into **actionable segments**.
* **Enhanced Readability:** The code uses a "clean UI" approach—removing the top and right borders (spines), using a soft background color (`#F8F9FA`), and adding white grid lines—to ensure the focus remains entirely on the data.
* **Direct Value Mapping:** By using `bar_label` with extra padding, the exact customer counts are placed at the end of each bar, making the chart function as both a visual aid and a summary report.

### What the Output Shows 
The chart reveals a **high-value customer skew**, meaning the business is exceptionally good at attracting and retaining high spenders:
* **The Power Segment (Top Tier):** The "67-100" range is your largest category by far, with **820 customers**. This indicates that a huge portion of your base consists of "Premium" or "Loyal" spenders.
* **The Core Middle:** The "50-66" range follows strongly with **680 customers**. Together with the top tier, these two groups represent the vast majority of your business activity.
* **The Plateau:** Between the "20-29" and "30-39" ranges, the number of customers is almost identical (**320 and 310 respectively**), showing a consistent "casual" shopper base.
* **Low Engagement:** There is very little "bottom-tier" activity. Only **100 customers** have a spending score of 0-4. 
* **Business Health:** This visualization shows an "Inverted Pyramid" distribution. Usually, businesses have many low-spenders and few high-spenders; your data shows the opposite, which suggests a **highly premium or luxury-leaning brand** where most customers are willing to spend significantly.

**In Short:** The visualization proves you have a "High-Value" customer base where the majority of your audience consists of your most profitable spenders.

<img width="985" height="590" alt="image" src="https://github.com/user-attachments/assets/363acf02-c9e0-4d46-a6bd-1eab8aa76691" />

### STEP 5: SELECTING FEATURES FOR CLUSTERING

**1.This is used to prepare your data for Machine Learning (specifically clustering or segmenting your customers).**

| Component | What it does | Why it is used |
| :--- | :--- | :--- |
| **`customer_data`** | Refers to your main dataset (the DataFrame). | To tell Python which source of information to look at. |
| **`.iloc`** | Stands for "Integer Location." | To select data based on its numerical position (index) rather than its name. |
| **`:`** | The "slice" operator for rows. | To ensure the model includes **every single customer** in the dataset, not just a few. |
| **`[3, 4]`** | Selects the 4th and 5th columns. | To isolate **Annual Income** and **Spending Score**, the two variables that define customer behavior. |
| **`.values`** | Converts the table into a NumPy array. | Machine Learning algorithms require **raw numbers** in an array format to perform mathematical calculations. |

This is the **"Feature Selection"** step. It strips away irrelevant information like "Customer ID" or "Gender" and creates a clean matrix of numbers ($x$) that represents the relationship between how much a customer earns versus how much they spend. This matrix is the primary input used for clustering algorithms (like K-Means) to find patterns in your data.

**2)This  is the core of the **"Elbow Method,"** a technique used to find the optimal number of clusters for your data.**

| Component | What it is | Why it's used |
| :--- | :--- | :--- |
| **`wcss = []`** | An empty list. | To store the "Error Score" (WCSS) for each cluster count. |
| **`for i in range(1, 11)`** | A loop from 1 to 10. | To test how well the data fits if we divide it into 1 group, then 2, then 3... up to 10. |
| **`init='k-means++'`** | A smart initialization trick. | To speed up convergence and avoid a "bad start" where the algorithm gets stuck. |
| **`kmeans.fit(x)`** | The training command. | To apply the K-Means math to your Income and Spending data (`x`). |
| **`kmeans.inertia_`** | The WCSS value. | To measure how tightly grouped the customers are inside their clusters. |

### **The  Logic**
* **WCSS (Within-Cluster Sum of Squares):** This measures the distance between each customer and the center of their cluster. A lower WCSS means the customers in a group are very similar to each other.
* **The Goal:** We want a low WCSS, but if every customer has their own cluster, the score is zero (which is useless). We use this loop to find the "Sweet Spot"—the point where adding more clusters no longer significantly improves the score.

### **The Result**
After this code runs, you will have a list of 10 numbers. When you plot them, you look for the **"Elbow"** (the point where the graph stops dropping sharply and flattens out). That "elbow" tells you exactly how many natural segments exist in your customer base.

**3)Creates a professional visualization known as the **Elbow Method Graph**. This is a diagnostic tool used in K-Means clustering to determine the optimal number of groups (clusters) for your customer data.**

* **Visualization Engine:** It uses **Matplotlib** to plot a line graph where the x-axis is the number of clusters (1–10) and the y-axis is the **WCSS** (Within-Cluster Sum of Squares).
* **Dynamic Labeling:** The `for` loop and `plt.annotate` functions are used to place the exact WCSS values next to each data point. It uses "Smart Placement" (offsetting text to the right during the steep drop and above during the flat part) so the text never overlaps the line.
* **Styling:** The code uses high-contrast colors (`#e74c3c` red), dashed lines, and large markers to make the "break point" of the graph obvious to stakeholders.

### **Output**
It tells a clear story about how your customers should be segmented:

* **The Steep Drop (Clusters 1–3):** Notice the massive jump from **269,981** to **106,348**. This means that splitting your customers into 2 or 3 groups provides a huge increase in "closeness" or similarity within each group.
* **The "Elbow" (The Optimal Point):** The graph shows a sharp bend or "elbow" at **5 clusters**. 
    * Before 5, the line is dropping rapidly.
    * After 5, the line flattens out (from **44,448** down to **23,103**), meaning that adding more clusters provides "diminishing returns."
* **The Conclusion:** Based on this **5 is the magic number**. Dividing your customer base into exactly 5 segments will give you the most statistically significant groups without overcomplicating your marketing strategy.

**In short:** It builds a decision-making map. The "elbow" at 5 proves that your data naturally settles into five distinct customer personas.

<img width="1035" height="656" alt="image" src="https://github.com/user-attachments/assets/ef033628-2ce7-4dda-95e9-37a5c4e75cd3" />
