# Data Visualization - Part 3

**Written by: Syed Muhammad Awais Raza**  
[LinkedIn](https://www.linkedin.com/in/syed-muhammad-awais-raza-905317278/) | [Email](mailto:awaisraza5424@gmail.com) | [GitHub](https://github.com/awai1s)


## Data Visualization Using Plotly 
***Table of Contents***
- [Data Visualization - Part 3](#data-visualization---part-3)
  - [Data Visualization Using Plotly](#data-visualization-using-plotly)
  - [Plotting Using Plotly](#plotting-using-plotly)
    - [1. **3D Scatter Plot**](#1-3d-scatter-plot)
    - [2. **3D Surface Plot**](#2-3d-surface-plot)
    - [3. **Sunburst Chart**](#3-sunburst-chart)
    - [4. **Treemap**](#4-treemap)
    - [5. **Chord Diagram**](#5-chord-diagram)
    - [6. **Violin Plot**](#6-violin-plot)


---
## Plotting Using Plotly


Plotly is a graphing library that makes interactive plots with high-quality visuals. It supports a wide range of plots and charts and is particularly known for its interactivity, which allows users to explore data in more detail. Plotly integrates well with Pandas and can be used in web applications and dashboards.

_**Example Plots**_

### 1. **3D Scatter Plot**

A 3D scatter plot adds a third dimension to the traditional scatter plot, making it possible to visualize relationships between three variables.

```python
import plotly.graph_objects as go

# Sample data
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]
z = [5, 6, 2, 3, 12]

# Creating a 3D scatter plot
fig = go.Figure(data=[go.Scatter3d(x=x, y=y, z=z, mode='markers')])
fig.update_layout(title='3D Scatter Plot', scene=dict(xaxis_title='X-axis', yaxis_title='Y-axis', zaxis_title='Z-axis'))
fig.show()
```
![3D Scatter Plot](3Scatterplot.jpg)
### 2. **3D Surface Plot**

A 3D surface plot is used to visualize three-dimensional data as a continuous surface, providing insights into the structure and relationships within the data.

```python
import numpy as np

# Sample data
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
x, y = np.meshgrid(x, y)
z = np.sin(np.sqrt(x**2 + y**2))

# Creating a 3D surface plot
fig = go.Figure(data=[go.Surface(z=z, x=x, y=y)])
fig.update_layout(title='3D Surface Plot', scene=dict(xaxis_title='X-axis', yaxis_title='Y-axis', zaxis_title='Z-axis'))
fig.show()
```
![3D Surface Plot](3Surfaceplot.jpg)
### 3. **Sunburst Chart**

A sunburst chart is used to visualize hierarchical data, showing relationships between levels in a hierarchy with radial segments.

```python
import plotly.express as px

# Sample data
import pandas as pd
data = pd.DataFrame({
    'labels': ['Parent', 'Child 1', 'Child 2', 'Grandchild 1', 'Grandchild 2'],
    'parents': ['', 'Parent', 'Parent', 'Child 1', 'Child 1'],
    'values': [10, 20, 30, 40, 50]
})

# Creating a sunburst chart
fig = px.sunburst(data, names='labels', parents='parents', values='values')
fig.update_layout(title='Sunburst Chart')
fig.show()
```
![Sunburst Chart](3Sunburstplot.jpg)
### 4. **Treemap**

A treemap is a hierarchical visualization that uses nested rectangles to display proportions within a hierarchy.

```python
# Sample data
import pandas as pd
data = pd.DataFrame({
    'labels': ['A', 'B', 'C', 'D', 'E'],
    'parents': ['', 'A', 'A', 'B', 'B'],
    'values': [10, 20, 30, 15, 25]
})

# Creating a treemap
fig = px.treemap(data, names='labels', parents='parents', values='values')
fig.update_layout(title='Treemap')
fig.show()
```
![Treemap](3Treemap.jpg)
### 5. **Chord Diagram**

A chord diagram is used to visualize relationships between entities in a circular layout, showing the flow between different segments.

```python
import plotly.graph_objects as go

# Sample data
import pandas as pd
data = pd.DataFrame({
    'source': ['A', 'A', 'B', 'B', 'C', 'C'],
    'target': ['B', 'C', 'A', 'C', 'A', 'B'],
    'value': [10, 20, 30, 40, 50, 60]
})

# Creating a chord diagram
fig = go.Figure(data=[go.Sankey(
    node=dict(pad=15, thickness=20, line=dict(color='black', width=0.5), label=['A', 'B', 'C']),
    link=dict(source=[0, 0, 1, 1, 2, 2], target=[1, 2, 0, 2, 0, 1], value=[10, 20, 30, 40, 50, 60])
)])
fig.update_layout(title='Chord Diagram')
fig.show()
```
![Chord Diagram](3ChordDiagram.jpg)

### 6. **Violin Plot**

A violin plot combines a box plot with a kernel density plot, showing the distribution of the data across different categories.

```python
import plotly.express as px

# Sample data
import seaborn as sns
iris = sns.load_dataset('iris')

# Creating a violin plot
fig = px.violin(iris, y="sepal_length", color="species", box=True, points="all")
fig.update_layout(title='Violin Plot')
fig.show()
```
![Violin Plot](3VoilonPlot.jpg)

---------------------------------
