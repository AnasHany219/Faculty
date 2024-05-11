
1. **Imports**: 
   - 🛠️ **Setup**: Import the libraries needed for data handling, visualization, model training, and evaluation.
   
   ```python
   # Cool Imports
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   from sklearn.model_selection import train_test_split
   from sklearn.linear_model import LinearRegression
   from sklearn import metrics
   ```

2. **Linear Regression Explained**: 
   - 📊 **What is it?** Linear regression is like finding the best-fitting line through scattered points. It helps predict a continuous outcome based on one or more predictor variables.
   
3. **Data Splitting**: 
   - 🎯 **Objective:** Divide data into predictors (X) and the outcome (y), then split them into training and testing sets.
   - 🧩 **Implementation:** We slice the dataset into X (features) and y (target), then split them into training and testing portions. 

   ```python
   # Load dataset 📚
   dataset = pd.read_csv('student_scores.csv')

   # Split features and target variable 🎯
   X = dataset.iloc[:, :-1]
   y = dataset.iloc[:, 1]

   # Split dataset into train and test sets 🧩
   X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.4, random_state=0)
   ```

4. **Training the Model**: 
   - 🚂 **Process:** Train a linear regression model using the training data.
   
   ```python
   # Train linear regression model 🚂
   regressor = LinearRegression()
   regressor.fit(X_train, y_train)
   ```

5. **Prediction**: 
   - 🔮 **Forecasting:** Predict the outcome variable using the test data.
   
   ```python
   # Predict on test set 🔮
   y_pred = regressor.predict(X_test)
   ```

6. **Evaluation Metrics**:
   - 📏 **Metrics Used:** To gauge how well our model performs, we calculate Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE).
   - 📉 **Interpretation:** Lower values of these metrics mean our model is better at predictions.
   
   ```python
   # Evaluation metrics 📏
   mae = metrics.mean_absolute_error(y_test, y_pred)
   mse = metrics.mean_squared_error(y_test, y_pred)
   rmse = np.sqrt(mse)
   print('Mean Absolute Error:', mae)
   print('Mean Squared Error:', mse)
   print('Root Mean Squared Error:', rmse)
   ```

7. **Visualization**:
   - 📊 **Graphical Insight:** Plot the actual data points against the predicted values to visually understand how well our model fits the data.
   
   ```python
   # Visualize results 📊
   df = pd.DataFrame({'Actual': y_test, 'Predicted': y_pred})
   print(df)

   # Plotting 📈
   plt.figure(figsize=(10, 6))
   plt.scatter(X_test, y_test, color='black', label='Actual')
   plt.plot(X_test, y_pred, color='blue', linewidth=1, label='Predicted')
   plt.title('Hours vs Percentage')
   plt.xlabel('Hours Studied')
   plt.ylabel('Percentage Score')
   plt.legend()
   plt.show()
   ```

![[Linear-Regression.png]]