# Comprehensive Guide to Pandas for Data Science (Beginner to Advanced)

## Table of Contents

---

Pandas is an essential Python library for data manipulation and analysis, offering powerful data structures like Series (1D) and DataFrame (2D). These structures make it easier to handle and analyze structured data.

### Installation
```bash
pip install pandas   # For virtual environments in Python
conda install pandas # For Anaconda virtual environments
```

Below is a curated list of **essential pandas functions** that are commonly used for tasks like data cleaning, manipulation, exploration, and analysis in **data science** and **machine learning** projects.

---

### **1. Creating DataFrames**
- `pd.DataFrame()`: Converts lists, dictionaries, or arrays into a DataFrame.
- `pd.Series()`: Converts a list or array into a Series (1D structure).

### **2. Inspecting Data**
- `df.head()`: Displays the first 5 rows of the DataFrame.
- `df.tail()`: Displays the last 5 rows of the DataFrame.
- `df.shape`: Shows the number of rows and columns in the DataFrame.
- `df.info()`: Provides summary information about the DataFrame, including data types and non-null counts.
- `df.describe()`: Generates basic statistics for numerical columns.
- `df.columns`: Lists the column names.
- `df.index`: Lists the index labels.

### **3. Selecting Data**
- `df['column_name']`: Selects a single column.
- `df[['col1', 'col2']]`: Selects multiple columns.
- `df.loc[]`: Selects data based on labels (rows and columns).
- `df.iloc[]`: Selects data based on integer index positions (rows and columns).
- `df.at[]`: Retrieves a specific value by row and column labels.
- `df.iat[]`: Retrieves a specific value by integer row and column positions.

### **4. Filtering Data**
- `df[df['column'] > value]`: Filters rows based on conditions.
- `df.query()`: Filters rows using a query expression (similar to SQL).
- `df.isnull()`: Identifies missing values.
- `df.notnull()`: Identifies non-missing values.
- `df.dropna()`: Removes rows with missing data.
- `df.fillna()`: Fills missing data with a specified value.

### **5. Cleaning Data**
- `df.drop()`: Drops rows or columns by label or index.
- `df.rename()`: Renames columns or row labels.
- `df.replace()`: Replaces specific values in the DataFrame.
- `df.astype()`: Changes the data type of a column.

### **6. Aggregation and Grouping**
- `df.groupby()`: Groups data by one or more columns.
- `df.agg()`: Applies multiple aggregation operations on grouped data.
- `df.sum()`, `df.mean()`, `df.median()`, `df.count()`: Calculates basic aggregation functions.
- `df.pivot_table()`: Creates a pivot table for multi-dimensional data aggregation.

### **7. Sorting and Ordering**
- `df.sort_values()`: Sorts data based on one or more columns.
- `df.sort_index()`: Sorts data based on the index.

### **8. Merging and Joining DataFrames**
- `pd.merge()`: Merges DataFrames using common columns or indices (SQL-like join).
- `df.join()`: Joins DataFrames on their index.
- `pd.concat()`: Concatenates DataFrames along rows (axis=0) or columns (axis=1).

### **9. Reshaping Data**
- `df.melt()`: Converts data from wide format to long format.
- `df.pivot()`: Converts data from long format to wide format.
- `df.stack()`: Converts columns into rows (MultiIndex).
- `df.unstack()`: Converts rows into columns (MultiIndex).

### **10. Time Series Analysis**
- `pd.to_datetime()`: Converts a column or series into a datetime object.
- `df.resample()`: Resamples time-series data to a different frequency (e.g., monthly, weekly).
- `df.shift()`: Shifts data forward or backward by a specified number of periods (useful for creating lag features).
- `df.rolling()`: Creates a rolling window for computing statistics like moving averages.

### **11. Handling Duplicates**
- `df.duplicated()`: Checks for duplicate rows in the DataFrame.
- `df.drop_duplicates()`: Removes duplicate rows.

### **12. Handling Categorical Data**
- `df.astype('category')`: Converts a column to a categorical data type.
- `df.get_dummies()`: Converts categorical columns into dummy variables (one-hot encoding).

### **13. Basic Data Visualization**
- `df.plot()`: A simple way to plot data using Matplotlib.
    - `df['column'].plot(kind='line')`: Line plot.
    - `df['column'].plot(kind='bar')`: Bar plot.
    - `df.plot(kind='scatter', x='col1', y='col2')`: Scatter plot.
- `df.hist()`: Plots histograms for all numerical columns.

### **14. String Operations**
- `df['column'].str.contains()`: Checks if a string is present in each entry of a column.
- `df['column'].str.split()`: Splits strings into lists of substrings.
- `df['column'].str.replace()`: Replaces parts of strings in the column.
- `df['column'].str.upper()`, `df['column'].str.lower()`: Converts text to uppercase or lowercase.

### **15. Sampling**
- `df.sample()`: Returns a random sample of the DataFrame (can specify the number of rows).
- `df.sample(frac=0.1)`: Samples 10% of the DataFrame.

### **16. Indexing and Setting Index**
- `df.set_index()`: Sets one or more columns as the index of the DataFrame.
- `df.reset_index()`: Resets the index of the DataFrame.

### **17. Applying Custom Functions**
- `df.apply()`: Applies a custom function along the axis of the DataFrame (either row-wise or column-wise).
- `df.applymap()`: Applies a function element-wise to the entire DataFrame.
- `df.map()`: Applies a function element-wise to a Series.

### **18. Working with Large Datasets**
- `df.memory_usage()`: Displays memory usage of each column (helpful for large datasets).
- `df.sample(n=1000)`: Samples 1000 rows from the DataFrame for analysis.

### **19. Exporting Data**
- `df.to_csv()`: Exports data to a CSV file.
- `df.to_excel()`: Exports data to an Excel file.
- `df.to_sql()`: Exports data to a SQL database.
- `df.to_json()`: Exports data to a JSON file.

### **20. Advanced Data Wrangling**
- `df.pivot_table()`: Creates a pivot table for multi-dimensional aggregation.
- `df.crosstab()`: Computes a cross-tabulation of two or more variables.
- `df.query()`: Filters data using a query expression similar to SQL.

---

### Conclusion
These functions are the **core tools** for data manipulation and analysis in **pandas**. Mastering them is crucial for any data scientist or machine learning practitioner, as they will significantly enhance your ability to clean, prepare, analyze, and visualize data efficiently. With these tools, you'll be well-equipped to tackle a variety of data-related challenges.
