# Data File

| Country | Age | Salary | Purchased |
| ------- | --- | ------ | --------- |
| France  | 44  | 72000  | No        |
| Spain   |     | 48000  | Yes       |
| Germany | 30  | 54000  | No        |
| Spain   | 38  | 61000  | No        |
| Germany | 40  |        | Yes       |
| France  | 35  | 58000  | Yes       |
| Spain   |     | 52000  | No        |
| France  | 48  | 79000  | Yes       |
| Germany | 50  | 83000  | No        |
| France  | 37  | 67000  | Yes       |
# Data Encoding 🏷️

### Label Encoding

- Label encoding is a technique used to convert categorical variables into numerical format. 
- Each category is assigned a unique numerical value, allowing machine learning algorithms to interpret them more effectively. 

```python
import pandas as pd
from sklearn.preprocessing import LabelEncoder

# Read the dataset
df = pd.read_csv("Data.csv")

# Initialize LabelEncoder
label_encoder = LabelEncoder()

# Label Encoding for 'Purchased'
df['Purchased'] = label_encoder.fit_transform(df['Purchased'])

# Display the dataset with encoded features
print(df)
```

**Output:**
```
   Country  Age   Salary  Purchased
0   France   44  72000         0
1    Spain   NaN  48000        1
2  Germany   30  54000         0
3    Spain   38  61000         0
4  Germany   40     NaN        1
5   France   35  58000         1
6    Spain   NaN  52000        0
7   France   48  79000         1
8  Germany   50  83000         0
9   France   37  67000         1
```

In this output:
- The 'Purchased' column has been successfully encoded, with 'No' transformed to 0 and 'Yes' transformed to 1.
- Other columns remain unchanged.

### One-Hot Encoding 🌟

- One-hot encoding is a powerful technique to transform categorical variables into a format that can be provided to machine learning algorithms.
- Creates binary columns for each category, indicating its presence or absence.

```python
import pandas as pd
from sklearn.preprocessing import OneHotEncoder

# Read the dataset
db = pd.read_csv("Data.csv")

# Initialize OneHotEncoder
hot = OneHotEncoder()

# One-Hot Encoding for 'Country'
hot_encoded = hot.fit_transform(db[['Country']]).toarray()

# Convert one-hot encoded features into DataFrame and concatenate with original dataset
hot_df = pd.get_dummies(db, columns=['Country'])

# Display the dataset with encoded features
print(hot_df)
```

**Output:**
```
    Age   Salary Purchased  Country_France  Country_Germany  Country_Spain
0  44.0  72000.0        No               1                0              0
1   NaN  48000.0       Yes               0                0              1
2  30.0  54000.0        No               0                1              0
3  38.0  61000.0        No               0                0              1
4  40.0      NaN       yes               0                1              0
5  35.0  58000.0       Yes               1                0              0
6   NaN  52000.0        No               0                0              1
7  48.0  79000.0       Yes               1                0              0
8  50.0  83000.0        No               0                1              0
9  37.0  67000.0       Yes               1                0              0
```

# Data Normalization 📏

### StandardScaler

- `StandardScaler` is a preprocessing technique that standardizes features by `removing` the `mean` and `scaling` to unit variance. 
- We use `StandardScaler` to transform the `Age` and `Salary` columns in this example. 
- The `fit_transform()` method first calculates the `mean` and `standard deviation` of the data and then `standardizes` the data using these statistics. 
- This ensures that the standardized features have a `mean of 0` and a `standard deviation of 1`, making them suitable for machine learning algorithms that assume normally distributed data.

1. **Calculate the Mean**: For each feature, calculate the mean value $\large\mu$ across all data points in the feature.
2. **Calculate the Standard Deviation**: For each feature, calculate the standard deviation $\large\sigma$ across all data points in the feature.
3. **Standardize the Data**: For each data point in each feature, subtract the mean $\large\mu$ and divide by the standard deviation $\large\sigma$.
$$X_{scaled} = \frac{{X - \mu}}{{\sigma}}$$

```python
import pandas as pd
from sklearn.preprocessing import StandardScaler

# Read the dataset
df = pd.read_csv("Data.csv")

# Initialize StandardScaler
scaler = StandardScaler()

# Fit and transform the selected columns ('Age' and 'Salary')
# - Fit: Calculates the mean and standard deviation of the data
# - Transform: Standardizes the data using the calculated mean and standard deviation
df[['Age', 'Salary']] = scaler.fit_transform(df[['Age', 'Salary']])

# Display the standardized dataset
print(df)
```

**Output:**
```
   Country       Age    Salary Purchased
0   France  0.595257  0.711013        No
1    Spain       NaN -1.364376       Yes
2  Germany -1.627035 -0.845529        No
3    Spain -0.357154 -0.240207        No
4  Germany -0.039684       NaN       yes
5   France -0.833360 -0.499631       Yes
6    Spain       NaN -1.018478        No
7   France  1.230197  1.316334       Yes
8  Germany  1.547668  1.662233        No
9   France -0.515889  0.278640       Yes
```
### Min-Max Scaling 📏

- Min-Max Scaling blows through your data, ensuring that it falls within a specified range, typically between 0 and 1. 
$$X_{scaled} = \frac{{X - X_{min}}} {{X_{max} - X_{min}}}$$
- Suppose we have a dataset with numerical features, 'Age' and 'Salary', and we want to scale these features using Min-Max Scaling:

```python
import pandas as pd
from sklearn.preprocessing import MinMaxScaler

# Read the dataset
df = pd.read_csv("Data.csv")

# Initialize MinMaxScaler
scaler = MinMaxScaler()

# Fit and transform the selected columns
df[['Age', 'Salary']] = scaler.fit_transform(df[['Age', 'Salary']])

# Display the scaled dataset
print(df)
```

**Output:**

```
   Country   Age    Salary Purchased
0   France  0.70  0.685714        No
1    Spain   NaN  0.000000       Yes
2  Germany  0.00  0.171429        No
3    Spain  0.40  0.371429        No
4  Germany  0.50       NaN       yes
5   France  0.25  0.285714       Yes
6    Spain   NaN  0.114286        No
7   France  0.90  0.885714       Yes
8  Germany  1.00  1.000000        No
9   France  0.35  0.542857       Yes
```
# Dealing with missing values 🕵️‍♂️

### **SimpleImputer 🕵️‍♂️**

- `SimpleImputer` comes to the rescue when your dataset has missing values, filling them in with specified strategies like `mean`, `median`, `mode`, `most_frequent`, or a `constant value`. 

```python
import pandas as pd
from sklearn.impute import SimpleImputer

# Read the dataset
df = pd.read_csv("Data.csv")

# Initialize SimpleImputer with the mean strategy
imputer = SimpleImputer(strategy='mean')

# Impute missing values in the 'Age' and 'Salary' columns
df[['Age', 'Salary']] = imputer.fit_transform(df[['Age', 'Salary']])

# iloc[rows, columns] -> integer-location based indexing
# iloc[:, 1:3] -> all rows and column 1, 2
# imputer.fit(df.iloc[:, 1:3])
# df.iloc[:, 1:3] = imputer.transform(df.iloc[:, 1:3])

# Display the dataset with imputed values
print(df)
```

**Output:**
```
   Country    Age        Salary Purchased
0   France  44.00  72000.000000        No
1    Spain  40.25  48000.000000       Yes
2  Germany  30.00  54000.000000        No
3    Spain  38.00  61000.000000        No
4  Germany  40.00  63777.777778       yes
5   France  35.00  58000.000000       Yes
6    Spain  40.25  52000.000000        No
7   France  48.00  79000.000000       Yes
8  Germany  50.00  83000.000000        No
9   France  37.00  67000.000000       Yes
```

[[Section 4 - Data preprocessing]]