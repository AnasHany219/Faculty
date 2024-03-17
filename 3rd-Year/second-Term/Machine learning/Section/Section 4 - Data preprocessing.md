# Feature selection and dimensionality reduction

- Feature selection is the process of selecting a subset of relevant features (variables) from a dataset to build predictive models. 
- Dimensionality reduction is a related technique that involves reducing the number of features in the dataset while preserving the most important information.
## Recursive Feature Elimination $(RFE)$

- `Recursive Feature Elimination (RFE)` is a feature selection technique that works by recursively `removing` the least important features from the dataset. 
- It repeatedly `fits the model` and `ranks the features` based on their importance. 
- Then, it `removes the least important features` and repeats the process until the desired number of features is reached.
### Example: 

1. **Import Libraries**: We import necessary libraries including `RFE` (for Recursive Feature Elimination), `svm` (for Support Vector Machine model), and `pandas` (for data manipulation).

```python
	from sklearn.feature_selection import RFE
	from sklearn import svm
	import pandas as pd
```

2. **Read the Dataset**: We read the dataset from the CSV file named "ds.csv" into a DataFrame called `data`.

```python
	# Read the dataset (assuming 'ds.csv' contains the data)
	data = pd.read_csv('ds.csv')
```

3. **Separate Features and Target Variable**: We separate the features (stored in variable `x`) and the target variable (stored in variable `y`) from the dataset.

```python
	# Separate features (x) and target variable (y)
	x = data.iloc[:, :-1]  # Features (all columns except the last one)
	y = data.iloc[:, -1]   # Target variable (last column)
```

4. **Create SVM Model**: We create an SVM model with a linear kernel. This model will be used in the Recursive Feature Elimination process.

```python
	# Create an SVM model with linear kernel
	model = svm.SVC(kernel='linear')
```

5. **Initialize RFE**: We initialize Recursive Feature Elimination (RFE) with the SVM model, specifying `n_features_to_select=10` to select 10 features.

```python
	# Initialize Recursive Feature Elimination (RFE) with SVM model
	rfe = RFE(model, n_features_to_select=10)
```

6. **Fit RFE to Data**: We fit the RFE object to the features (`x`) and the target variable (`y`).

```python
	# Fit RFE to the data
	rfe.fit(x, y)
```

7. **Retrieve Selected Features**: We retrieve the selected features mask (`selected_features_mask`) and their rankings (`feature_rankings`) from the RFE object.

```python
	# Retrieve the selected features and their rankings
	selected_features_mask = rfe.support_  # Boolean mask indicating selected features
	feature_rankings = rfe.ranking_        # Feature rankings
```

8. **Print Selected Features and Rankings**: We print the selected features mask and their rankings for inspection.

```python
	# Print the selected features mask and their rankings
	print("Selected Features Mask:", selected_features_mask)
	print("Feature Rankings:", feature_rankings)
```

9. **Create New DataFrame**: We create a new DataFrame (`selected_data`) containing only the selected features. We use the selected features mask to select columns from the original feature matrix `x`. Additionally, we add the target variable `y` to this DataFrame.

```python
	# Create a new DataFrame with only the selected features and the target variable
	selected_data = x[x.columns[selected_features_mask]]  # Select columns based on the filter mask
	selected_data["outcome"] = y  # Add the target variable to the DataFrame
```

10. **Save to CSV**: Finally, we save the new dataset with selected features and the target variable to a CSV file named "newdata.csv". Setting `index=False` ensures that the DataFrame index is not saved as a separate column in the CSV file.

```python
	# Save the new dataset with selected features to a CSV file
	selected_data.to_csv("newdata.csv", index=False)
```

## Principal Component Analysis $(PCA)$

# Dealing with imbalanced data

## Oversampling $SMOTE$
