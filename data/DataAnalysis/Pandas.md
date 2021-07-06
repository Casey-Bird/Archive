# Pandas module in Python

### Initialization
```python
import pandas as pd # pd is the conventional method for importing this module.
```

```python
data_frame = pd.read_csv("path/to/csv.csv")
```

### Functions

```python
data_frame.head() # Shows top few entries in the dataset.
data_frame.shape() # Displayes how many rows, columns the dataset has.
data_frame.info() # Gives basic information about the different columns.
data_frame.describe() # Gives some statistical properties of a given dataset.
data_frame.value_counts() # Returns value counts
```

```python
data_frame['Column'].head() # .describe(), .shape(), .info(), etc...
data_frame['New_Column'] = data_frame['Column'] + data_frame['Column2'] # Simple column creation
```



