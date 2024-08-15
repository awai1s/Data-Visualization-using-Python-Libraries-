
# Data Visualization - Part 4

**Written by: Syed Muhammad Awais Raza**  
[LinkedIn](https://www.linkedin.com/in/syed-muhammad-awais-raza-905317278/) | [Email](mailto:awaisraza5424@gmail.com) | [GitHub](https://github.com/awai1s)

---
## Different Plots with code

---

***Table of Contents***
- [Data Visualization - Part 4](#data-visualization---part-4)
  - [Different Plots with code](#different-plots-with-code)
  - [Bar Chart](#bar-chart)
  - [Pie Chart](#pie-chart)
  - [Histogram](#histogram)
  - [Scatter Plot](#scatter-plot)
  - [Line Chart](#line-chart)
  - [Heatmap](#heatmap)
  - [Boxplot](#boxplot)
  - [Area Chart](#area-chart)
  - [Spider or Radar Plot](#spider-or-radar-plot)
  - [Tree Map](#tree-map)
  - [Geographical Maps](#geographical-maps)
  - [Time Series Plots](#time-series-plots)
  - [Bubble Chart](#bubble-chart)
  - [Violin Plots](#violin-plots)

---

## Bar Chart

Python code:
```python
# import pandas and matplotlib.pyplot libraries
import pandas as pd
import matplotlib.pyplot as plt

# create a dictionary with sample data
data = {'Products': ['Product A', 'Product B', 'Product C'],
    'Sales': [100, 150, 80]}

# create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# plot the dataframe as a bar chart
df.plot(x='Products', y='Sales', kind='bar', legend=False)

# set the y-axis label
plt.ylabel('Sales')

# set the title of the plot
plt.title('Sales of different products')

# save the plot to a file
plt.savefig('bar_chart.png', dpi=300, bbox_inches='tight')

# display the plot
plt.show()
```

![bar_chart](Bplot.png)


## Pie Chart

Python code:
```python
# import pandas and matplotlib.pyplot libraries
import pandas as pd
import matplotlib.pyplot as plt

# create a dictionary with sample data
data = {'Products': ['Product A', 'Product B', 'Product C'],
        'Sales': [100, 150, 80]}

# create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# plot the dataframe as a pie chart
df.set_index('Products')['Sales'].plot(kind='pie', autopct='%1.1f%%', startangle=90)

# set the title of the plot
plt.title('Sales distribution of different products')

# save the plot to a file
plt.savefig('pie_chart.png', dpi=300, bbox_inches='tight')

# display the plot
plt.ylabel('')  # This is to remove the 'Sales' ylabel which is unnecessary in a pie chart
plt.show()
```
![pie_chart](pplot.png)

## Histogram

Python code:
```python
# import pandas and matplotlib.pyplot libraries
import pandas as pd
import matplotlib.pyplot as plt

# create a dictionary with sample data
data = {'Sales': [30,50,120,150,200,300,100, 150, 80, 120, 140, 130,
                  50,50,30,20,10,50,35,45,55,50,55,65,56,58,58,54,55,50,5,
                  110, 145, 105, 90, 115, 125, 135, 85, 95]}

# create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# plot the dataframe as a histogram
df['Sales'].plot(kind='hist', bins=5, edgecolor='black')

# set the x-axis and y-axis labels
plt.xlabel('Sales Value')
plt.ylabel('Number of Transactions')

# set the title of the plot
plt.title('Distribution of Sales Transactions')

# save the plot to a file
plt.savefig('histogram.png', dpi=300, bbox_inches='tight')

# display the plot
plt.show()
```
![histogram](Hplot.png)

## Scatter Plot

Python code:
```python
# import pandas and matplotlib.pyplot libraries
import pandas as pd
import matplotlib.pyplot as plt

# create a dictionary with sample data
data = {
    'Sales': [100, 150, 80, 120, 140, 130, 110, 145, 105, 90],
    'Profit': [50, 70, 40, 60, 75, 65, 55, 72, 52, 45]
}

# create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# plot the dataframe as a scatter plot
df.plot(x='Sales', y='Profit', kind='scatter')

# set the x-axis and y-axis labels
plt.xlabel('Sales Value')
plt.ylabel('Profit Value')

# set the title of the plot
plt.title('Relationship between Sales and Profit')

# save the plot to a file
plt.savefig('scatter_plot.png', dpi=300, bbox_inches='tight')

# display the plot
plt.show()
```
![scatter_plot](splot.png)

## Line Chart

Python code:
```python
# import pandas and matplotlib.pyplot libraries
import pandas as pd
import matplotlib.pyplot as plt

# create a dictionary with sample data
data = {
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    'Monthly Sales': [100, 110, 105, 115, 120, 125, 130, 135, 140, 145, 150, 155]
}

# create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# plot the dataframe as a line chart
df.plot(x='Month', y='Monthly Sales', kind='line', marker='o')

# set the x-axis and y-axis labels
plt.xlabel('Month')
plt.ylabel('Sales Value')

# set the title of the plot
plt.title('Monthly Sales Trend over a Year')

# save the plot to a file
plt.savefig('line_chart.png', dpi=300, bbox_inches='tight')

# display the plot
plt.show()
```
![line_chart](lplot.png)


## Heatmap

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Sample correlation matrix
data = {
    'Product A': [1, 0.6, 0.8, 0.3],
    'Product B': [0.6, 1, 0.5, 0.7],
    'Product C': [0.8, 0.5, 1, 0.4],
    'Product D': [0.3, 0.7, 0.4, 1]
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(df, annot=True, cmap='viridis', vmin=0, vmax=1)

# Set the title of the plot
plt.title('Product Correlation Heatmap')

# Save the plot to a file
plt.savefig('heatmap.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![heatmap](Hmap.png)


## Boxplot

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt

# Sample data
data = {
    'Product A': [95, 85, 90, 100, 105, 110],
    'Product B': [100, 105, 95, 90, 115, 120],
    'Product C': [105, 110, 115, 120, 125, 130]
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the boxplot
df.boxplot(grid=False, vert=True, fontsize=10)

# Set the title of the plot
plt.title('Sales Distribution by Product')

# Set the y-axis label
plt.ylabel('Sales Value')

# Save the plot to a file
plt.savefig('boxplot.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![boxplot](boxplot.png)

## Area Chart

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Sample data
data = {
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
    'Sales': [100, 150, 180, 220, 270]  # Accumulated sales for

 each month
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the area chart
df.plot(x='Month', y='Sales', kind='area', alpha=0.5, figsize=(8, 5))

# Set the title and labels
plt.title('Sales Accumulation Over Months')
plt.xlabel('Month')
plt.ylabel('Sales Value')

# Save the plot to a file
plt.savefig('area_chart.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![area_chart](achart.png)

## Spider or Radar Plot

Python code:
```python
# import required libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from math import pi

# Sample data
labels = np.array(['A', 'B', 'C', 'D'])
values = np.array([4, 3, 2, 5])

# Number of variables
num_vars = len(labels)

# Compute angle for each axis
angles = np.linspace(0, 2 * np.pi, num_vars, endpoint=False).tolist()

# The plot is circular, so we need to "complete the loop" and append the start value to the end.
values = np.concatenate((values,[values[0]]))
angles += angles[:1]

# Plotting
fig, ax = plt.subplots(figsize=(6, 6), subplot_kw=dict(polar=True))
ax.fill(angles, values, color='red', alpha=0.25)
ax.plot(angles, values, color='red', linewidth=2, linestyle='solid')

# Labels for the axes
ax.set_yticklabels([])
ax.set_xticks(angles[:-1])
ax.set_xticklabels(labels)

# Set the title
plt.title('Spider Plot Example', size=15, color='red', y=1.1)

# Save the plot to a file
plt.savefig('spider_plot.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![spider_plot](spiderchart.png)

## Tree Map

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt
import squarify

# Sample data
data = {
    'Category': ['A', 'B', 'C', 'D'],
    'Value': [500, 300, 200, 400]
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the tree map
plt.figure(figsize=(8, 6))
squarify.plot(sizes=df['Value'], label=df['Category'], alpha=0.7)

# Set the title
plt.title('Tree Map Example')

# Save the plot to a file
plt.savefig('tree_map.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![treemap](treemap.png)


## Geographical Maps

Python code:
```python
# import required libraries
import geopandas as gpd
import matplotlib.pyplot as plt

# Load a map of countries
world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))

# Plot the world map
fig, ax = plt.subplots(figsize=(10, 7))
world.plot(ax=ax, color='lightblue', edgecolor='black')

# Set the title
plt.title('World Map')

# Save the plot to a file
plt.savefig('world_map.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![worldmap](geomaps.png)

## Time Series Plots

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt

# Sample time series data
data = {
    'Date': pd.date_range(start='2024-01-01', periods=10, freq='D'),
    'Value': [10, 20, 15, 30, 40, 35, 50, 60, 55, 70]
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the time series plot
plt.figure(figsize=(10, 6))
plt.plot(df['Date'], df['Value'], marker='o', linestyle='-')

# Set the title and labels
plt.title('Time Series Plot')
plt.xlabel('Date')
plt.ylabel('Value')

# Rotate x-axis labels
plt.xticks(rotation=45)

# Save the plot to a file
plt.savefig('time_series_plot.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![timeseries](timeseriesplot.png)

## Bubble Chart

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt

# Sample data
data = {
    'Category': ['A', 'B', 'C', 'D'],
    'X': [1, 2, 3, 4],
    'Y': [2, 3, 4, 5],
    'Size': [100, 200, 300, 400]
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the bubble chart
plt.figure(figsize=(8, 6))
plt.scatter(df['X'], df['Y'], s=df['Size'], alpha=0.5, c='blue', edgecolors='w', linewidth=2)

# Set the title and labels
plt.title('Bubble Chart Example')
plt.xlabel('X Value')
plt.ylabel('Y Value')

# Save the plot to a file
plt.savefig('bubble_chart.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![bubblechart](bubbleplot.png)

## Violin Plots

Python code:
```python
# import required libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Sample data
data = {
    'Category': ['A', 'A', 'A', 'B', 'B', 'B', 'C', 'C', 'C'],
    'Value': [10, 15, 12, 20, 25, 22, 30, 35, 32]
}

# Create a pandas dataframe from the dictionary
df = pd.DataFrame(data)

# Plotting the violin plot using seaborn
plt.figure(figsize=(8, 6))
sns.violinplot(x='Category', y='Value', data=df, inner='quartile')

# Set the title and labels
plt.title('Violin Plot Example')
plt.xlabel('Category')
plt.ylabel('Value')

# Save the plot to a file
plt.savefig('violin_plot.png', dpi=300, bbox_inches='tight')

# Display the plot
plt.show()
```
![violinplot](voilenplot.png)

