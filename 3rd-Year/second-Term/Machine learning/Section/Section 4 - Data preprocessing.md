# Feature selection and dimensionality reduction

- Feature selection is the process of selecting a subset of relevant features (variables) from a dataset to build predictive models. 
- Dimensionality reduction is a related technique that involves reducing the number of features in the dataset while preserving the most important information.
## Recursive Feature Elimination $(RFE)$

- `Recursive Feature Elimination (RFE)` is a feature selection technique.
- It iteratively `removes` the `least important features` from the dataset.
- The process continues until the desired number of features is `reached`.
- `RFE` improves` model performance` and `reduces overfitting`.
- It provides insights into feature importance and enhances model interpretability.
- `RFE` is useful for high-dimensional datasets and helps build efficient `machine learning models`.
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
- `Principal Component Analysis (PCA)` is a dimensionality reduction technique.
- It transforms `high-dimensional data` into a `lower-dimensional space`.
- PCA identifies the directions `principal components` that maximize variance in the data.
- Principal components are `orthogonal` and` capture different directions` of variation.
- PCA is used for `dimensionality reduction`, `visualization`, `noise reduction`, and `feature engineering`.
- It `simplifies` complex datasets while retaining essential information.
### Example: 

1. **Loading the Dataset**: Load the dataset `ds.csv` containing features and target variable.
```python
	import numpy as np
	import pandas as pd
	import matplotlib.pyplot as plt
	from sklearn.decomposition import PCA
	
	# Load the dataset
	data = pd.read_csv("ds.csv")
```
2. **Separating Features and Target**: Separate the features (`x`) from the target variable (`y`).
```python
	# Separate features (x) and target variable (y)
	x = data.iloc[:, :-1]
	y = data.iloc[:, -1]
```
3. **Performing PCA**: Initialize PCA and fit-transform the features to obtain the principal components.
```python
	# Perform PCA
	pca = PCA()
	pca.fit_transform(x)
```
4. **Explained Variance Ratio**: Calculate the explained variance ratio and the cumulative explained variance.
```python
	# Explained variance ratio
	exvar = pca.explained_variance_ratio_
	varsum = np.cumsum(exvar)
	print(exvar)
```
5. **Plotting Explained Variance Ratio**: Plot the individual and cumulative explained variance ratios to visualize the information captured by each principal component.
```python
	# Plot explained variance ratio
	plt.bar(range(0, len(exvar)), exvar, label='Individual explained variance')
	plt.step(range(0, len(varsum)), varsum, label='Cumulative explained variance')
	plt.ylabel('Explained variance ratio')
	plt.xlabel('Principal component index')
	plt.legend(loc='lower right')
	plt.show()
```
6. **Reducing Dimensionality**: Perform PCA again, this time specifying the number of principal components to keep (5 in this example).
```python
	# Reduce dimensionality to 5 principal components
	pca = PCA(n_components=5)
	principalDf = pd.DataFrame(data=pca.fit_transform(x), columns=['A', 'B', 'C', 'D', 'E'])
```
7. **Concatenating with Target Variable**: Combine the principal components with the target variable.
```python
	# Concatenate principal components with target variable
	finalDf = pd.concat([principalDf, y], axis=1)
```
8. **Saving Transformed Dataset**: Save the transformed dataset as `pcadata.csv` without indices and with headers.
```python
	# Save the transformed dataset
	finalDf.to_csv("pcadata.csv", index=False, header=True)
```
# Dealing with imbalanced data

- **Definition**: Imbalanced data refers to datasets where the classes are not evenly distributed, leading to biased models.
- **Challenges**: Imbalanced datasets can cause models to prioritize the majority class, leading to poor performance on minority classes.
- **Strategies**:
	- **Oversampling**: Increasing the number of instances in the minority class.
	- **Undersampling**: Reducing the number of instances in the majority class.
	- **Synthetic Sampling**: Generating synthetic instances for the minority class.

### Oversampling $(SMOTE)$

- **Definition**: SMOTE (Synthetic Minority Over-sampling Technique) is an oversampling technique used to address class imbalance by generating synthetic instances for the minority class.
- **Process**:
  1. **Identify Nearest Neighbors**: Find the k nearest neighbors for each minority class instance.
  2. **Generate Synthetic Instances**: Create new instances by interpolating between minority class instances and their nearest neighbors.
  3. **Balanced Dataset**: Repeat the process until the desired balance between classes is achieved.
### Example Explanation:

1. **Data Loading**: Load the dataset from the file 'bc.csv' using pandas.
```python
	# Import necessary libraries
	import numpy as np
	import pandas as pd
	from sklearn.model_selection import train_test_split
	from sklearn.metrics import classification_report
	from sklearn import svm
	from imblearn.over_sampling import SMOTE
	
	# Load the dataset
	data = pd.read_csv('bc.csv')
	
	# Display the shape of the dataset
	print("Dataset shape:", data.shape)
```
2. **Splitting Data**: Split the dataset into features (x) and the target variable (y) where x contains all columns except the last one, and y contains the last column.
```python
# Separate features (x) and target variable (y)
x = data.iloc[:, :-1] 
y = data.iloc[:, -1]
```
3. **Train-Test Split**: Divide the dataset into training and testing sets using the `train_test_split` function from scikit-learn. Here, 70% of the data is used for training (`x_train`, `y_train`), and 30% is reserved for testing (`x_test`, `y_test`).
```python
# Split the dataset into training and testing sets
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.3)
```
4. **Class Imbalance Checking (Before Oversampling)**: Print the counts of each class in the training set before applying oversampling. This helps to visualize the class distribution.
```python
# Display the counts of each class in the training set before oversampling
print("Before OverSampling # 1 =", sum(y_train == 1)) 
print("Before OverSampling # 0 =", sum(y_train == 0))
```
5. **Oversampling (SMOTE)**: Perform oversampling using the Synthetic Minority Over-sampling Technique (SMOTE) to balance the class distribution. The `fit_resample` function generates synthetic samples for the minority class to match the majority class.
```python
# Perform oversampling using SMOTE
sm = SMOTE()
x_res, y_res = sm.fit_resample(x_train, y_train)
```
6. **Class Imbalance Checking (After Oversampling)**: Print the counts of each class in the training set after applying SMOTE to verify that the class distribution has been balanced.
```python
# Display the counts of each class in the training set after oversampling
print("-----------------------------------------")
print("After OverSampling # 1 =", sum(y_res == 1)) 
print("After OverSampling # 0 =", sum(y_res == 0))
```