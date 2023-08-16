# 3D LEGO Bar Plot with Plotly

This Jupyter Notebook demonstrates how to create a 3D LEGO-style bar plot using the Plotly library. The plot is similar in style to ROOT's 2D histo bar plot representation.

<div class="center">
  <img src="https://github.com/DFreireF/legoplot/raw/main/docs/img/legoplot.png" alt="Legoplot Image" width="900">
</div>

## Prerequisites

You need the following libraries installed to run this notebook:

- Plotly
- NumPy
- Uproot
- os

You can install these libraries using the provided code snippet below or manually using pip.

## Installation

If you do not have the required libraries installed, you can run the following code in a Jupyter Notebook cell to install them:

```python
import importlib

# List of packages to import
packages_to_import = [
    ("plotly", "plotly.graph_objects", "go"),
    ("plotly", "plotly.io", "pio"),
    ("numpy", "numpy", "np"),
    ("uproot", "uproot", "uproot"),
    ("os", "os", "os")
]

# Loop through the packages and check if they are imported
for package_name, module_name, alias in packages_to_import:
    try:
        module = importlib.import_module(module_name)
        print(f"{alias} is already imported.")
    except ImportError:
        print(f"{alias} is not imported. Installing...")
        get_ipython().system(f'pip install {package_name}')
```
## Usage
```python
# Import the required libraries
import plotly.graph_objects as go
import plotly.io as pio
import numpy as np
import uproot
import os

# Define the lego3D function to create a 3D LEGO-style bar plot
def lego3D(x_position, y_position, counts, title='', x_title='x position', y_title='y position', z_title='counts',
           width=900, height=900, thickness=0.4, colorscale='jet', **kwargs):
    # ...

# Define the read_data function to load data from a CSV or ROOT file
def read_data(filename='simTe7MeV_pgData.csv'):
    # ...

# Load data using the read_data function
x, y, z = read_data(filename='simTe7MeV_pgData.csv')

# Create the 3D LEGO plot using the loaded data
fig = lego3D(x, y, z, colorscale='jet', opacity=0.9, flatshading=True, thickness=0.14)
fig.show()
```
