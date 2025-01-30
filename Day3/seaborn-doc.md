# Seaborn Documentation for Data Analytics and Data Analysis

## Introduction
Seaborn is a Python data visualization library built on top of Matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics, making it particularly useful for data analytics and data analysis.

## Installation
To install Seaborn, use the following command:
```sh
pip install seaborn
```

## Importing Seaborn
```python
import seaborn as sns
import matplotlib.pyplot as plt
```

## Built-in Datasets
Seaborn provides several built-in datasets that can be loaded using:
```python
data = sns.load_dataset("tips")
print(data.head())
```

## Basic Plotting with Seaborn

### 1. Scatter Plot
Used to show relationships between two continuous variables.
```python
sns.scatterplot(x="total_bill", y="tip", data=data)
plt.title("Scatter Plot Example")
plt.show()
```

### 2. Line Plot
Used to visualize continuous data trends over an interval.
```python
sns.lineplot(x="size", y="total_bill", data=data)
plt.title("Line Plot Example")
plt.show()
```

### 3. Bar Plot
Used for categorical comparisons.
```python
sns.barplot(x="day", y="total_bill", data=data)
plt.title("Bar Plot Example")
plt.show()
```

### 4. Histogram
Used to visualize the distribution of a dataset.
```python
sns.histplot(data["total_bill"], bins=30, kde=True)
plt.title("Histogram Example")
plt.show()
```

### 5. Box Plot
Used for detecting outliers and visualizing distributions.
```python
sns.boxplot(x="day", y="total_bill", data=data)
plt.title("Box Plot Example")
plt.show()
```

### 6. Violin Plot
A combination of box plot and density plot.
```python
sns.violinplot(x="day", y="total_bill", data=data)
plt.title("Violin Plot Example")
plt.show()
```

## Advanced Seaborn Features

### 1. Pair Plot
Used for visualizing pairwise relationships in a dataset.
```python
sns.pairplot(data)
plt.show()
```

### 2. Heatmap
Used for correlation analysis.
```python
sns.heatmap(data.corr(), annot=True, cmap="coolwarm")
plt.title("Heatmap Example")
plt.show()
```

### 3. Facet Grid
Used to plot subsets of data across multiple plots.
```python
g = sns.FacetGrid(data, col="sex")
g.map(sns.histplot, "total_bill")
plt.show()
```

### 4. Customizing Plots
#### Changing Styles
```python
sns.set_style("darkgrid")
```
#### Custom Color Palettes
```python
sns.set_palette("pastel")
```

## Saving Seaborn Figures
```python
plt.savefig("seaborn_plot.png")
```

## Conclusion
Seaborn is a powerful tool for data visualization, offering a variety of high-level plotting functions. For more details, refer to the [official Seaborn documentation](https://seaborn.pydata.org/).

