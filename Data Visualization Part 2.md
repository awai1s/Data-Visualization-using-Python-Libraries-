# Data Visualization - Part 2

**Written by: Syed Muhammad Awais Raza**  
[LinkedIn](https://www.linkedin.com/in/syed-muhammad-awais-raza-905317278/) | [Email](mailto:awaisraza5424@gmail.com) | [GitHub](https://github.com/awai1s)


## Data Visualization using Matplotlib and Seaborn
***Table of Contents***
- [Data Visualization - Part 2](#data-visualization---part-2)
  - [Data Visualization using Matplotlib and Seaborn](#data-visualization-using-matplotlib-and-seaborn)
  - [Matplotlib](#matplotlib)
    - [Explanation](#explanation)
    - [Example Plots](#example-plots)
      - [1. Line Plot](#1-line-plot)
      - [2. Bar Chart](#2-bar-chart)
      - [3. Histogram](#3-histogram)
      - [4. Scatter Plot](#4-scatter-plot)
  - [Seaborn](#seaborn)
    - [Explanation](#explanation-1)
    - [Example Plots](#example-plots-1)
      - [1. Distribution Plot](#1-distribution-plot)
      - [2. Box Plot](#2-box-plot)
      - [3. Heat Map](#3-heat-map)
      - [4. Pair Plot](#4-pair-plot)
  - [](#)
---

---
                            “A picture is worth a thousand words”
-----------

## Matplotlib

### Explanation

Matplotlib is a versatile and comprehensive library for creating static, animated, and interactive visualizations in Python. It is highly customizable and can be used to generate a wide variety of plots and charts, from simple line plots to complex 3D visualizations.

### Example Plots

#### 1. Line Plot

A line plot is used to display data points connected by straight lines. It is useful for visualizing trends over time.

```python
import matplotlib.pyplot as plt

# Sample data
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Creating a line plot
plt.plot(x, y, marker='o')
plt.title('Line Plot')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```
![Line Plot](Lineplot.jpg)

#### 2. Bar Chart

A bar chart represents data with rectangular bars, where the height of the bar is proportional to the value being represented.

```python
# Sample data
categories = ['A', 'B', 'C', 'D']
values = [10, 24, 36, 12]

# Creating a bar chart
plt.bar(categories, values)
plt.title('Bar Chart')
plt.xlabel('Categories')
plt.ylabel('Values')
plt.show()
```

![Barplot](Barplot.jpg)

#### 3. Histogram

A histogram is used to represent the distribution of a dataset by dividing the data into bins and counting the number of observations in each bin.

```python
# Sample data
data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

# Creating a histogram
plt.hist(data, bins=4)
plt.title('Histogram')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.show()
```
![Histogram](Histogram.jpg)
#### 4. Scatter Plot

A scatter plot displays data points as individual dots, showing the relationship between two variables.

```python
# Sample data
x = [1, 2, 3, 4, 5]
y = [2, 3, 4, 5, 6]

# Creating a scatter plot
plt.scatter(x, y)
plt.title('Scatter Plot')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```
![Scatterplot](Scatterplot.jpg)
## Seaborn

### Explanation

Seaborn is built on top of Matplotlib and provides a high-level interface for creating attractive and informative statistical graphics. It simplifies complex visualizations and integrates well with Pandas data structures.

### Example Plots

#### 1. Distribution Plot

A distribution plot shows the distribution of a dataset and can include a histogram and a kernel density estimate (KDE).

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample data
data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

# Creating a distribution plot
sns.distplot(data, kde=True, bins=4)
plt.title('Distribution Plot')
plt.show()
```
![Distributionplot](Distributionplot.jpg)

#### 2. Box Plot

A box plot (or whisker plot) displays the distribution of a dataset based on a five-number summary: minimum, first quartile, median, third quartile, and maximum.

```python
# Sample data
data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

# Creating a box plot
sns.boxplot(data=data)
plt.title('Box Plot')
plt.show()
```
![Boxplot](Boxplot.jpg)
#### 3. Heat Map

A heat map represents data in a matrix format, where individual values are represented by colors.

```python
import numpy as np

# Sample data
data = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Creating a heat map
sns.heatmap(data, annot=True, cmap='coolwarm')
plt.title('Heat Map')
plt.show()
```
![Heatmap](Heatmap.jpg)

#### 4. Pair Plot

A pair plot shows pairwise relationships in a dataset. It is useful for visualizing the relationships between multiple variables.

```python
# Sample data
iris = sns.load_dataset('iris')

# Creating a pair plot
sns.pairplot(iris)
plt.title('Pair Plot')
plt.show()
```
![Pairplot](Pairplot.jpg)
---

---

