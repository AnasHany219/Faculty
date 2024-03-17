## **DataFrame()**

- DataFrames are the backbone of data `manipulation` and `analysis` in Python, especially with the `pandas` library. 
- They're like virtual `spreadsheets`, allowing you to `organize`, `filter`, and `analyze` your data with ease.

- **Using a Dictionary as Data**:

    Data often comes in various formats, and Python makes it easy to work with them. Here's how you can turn a `dictionary` into a `DataFrame`:

    ```python
    import pandas as pd

    # Suppose you have a dictionary-like dataset
    data_dict = {
        'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [25, 30, 35],
        'City': ['New York', 'Los Angeles', 'Chicago']
    }

    # Convert dictionary to DataFrame
    df = pd.DataFrame(data_dict)

    # Display DataFrame
    print(df)
    ```

    Running this script will create a DataFrame that looks like this:

    ```
          Name  Age         City
    0    Alice   25     New York
    1      Bob   30  Los Angeles
    2  Charlie   35      Chicago
    ```
## **Dataset Reading**

- **Pandas:**
  ```python
  import pandas as pd

  # Read CSV file
  df = pd.read_csv("dataset.csv")
  ```

- **CSV Module**:
  ```python
  import csv

  # Read CSV file
  with open('data.csv', 'r') as file:
      reader = csv.reader(file)
      for row in reader:
          print(row)
  ```
## **Visualization using Seaborn**:

- `Seaborn` is a Python data visualization library based on matplotlib. 
- It provides a high-level interface for drawing attractive and informative statistical graphics. 
### 1. **Line Plot**:
   - A line plot displays data points connected by `straight line segments`.
   - Useful for showing `trends over time` or `continuous variables`.

```python
import pandas as pd
import seaborn as sns

# Generate sample data
db = pd.read_csv('Data.csv')

# Line Plot
line = sns.lineplot(data = db, x = 'Age', y = 'Salary')
```

![[Line-Plot.png| 300]]
### 2. **Scatter Plot**:
   - A scatter plot represents individual data points as `dots`.
   - Useful for visualizing the relationship between `two continuous variables`.

```python
import pandas as pd
import seaborn as sns

# Generate sample data
db = pd.read_csv('Data.csv')

# Scatter Plot
scatterplot = sns.scatterplot(data = db, x = 'Age', y = 'Salary')
```

![[Scatter-Plot.png | 300]]
### 3. **Box Plot**:
   - A box plot displays the distribution of `a continuous variable` through its `quartiles`.
   - Useful for identifying `outliers` and `comparing distributions`.

```python
import pandas as pd
import seaborn as sns

# Generate sample data
db = pd.read_csv('Data.csv')

# Box Plot
box = sns.boxplot(data = db, x = 'Age', y = 'Salary')
```

![[Box-Plot.png | 300]]

## **🔍 Analyze data using pandas_profiling report 📊**

1. **Install pandas_profiling**:   
	- Before diving into the expedition, make sure you have the pandas_profiling library on board. You can install it via pip:
   ```bash
   pip install pandas-profiling
   ```

2. **Generate a Report**:

   ```python
   import pandas as pd
   from pandas_profiling import ProfileReport

   # Read the dataset
   db = pd.read_csv("your_dataset.csv")

   # Generate and display the report
   ProfileReport(db)
   ```

   Replace `"your_dataset.csv"` with the path to your dataset file. This incantation will conjure a mesmerizing report filled with statistics, histograms, correlation matrices, and more.

3. **Interpret the Report**:
	- Once the report emerges, explore its contents carefully. 
	- Look for data distributions, missing values, variable correlations, and potential anomalies.

[[Section 3 - Data preprocessing]]