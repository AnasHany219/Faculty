## 📉 Regression

- **Regression Problem**: The output you desire is a continuous value `numeric`, such as a rating `a real number between 0 and 10` or the price of a house.
  - Predicting continuous outputs is termed regression.
## 🎯 What Do I Need to Predict These Outputs?

- **Features**: We'll refer to these as $x$ or $\mathbf{x}$ if they are vectors.
- **Training Examples**: Many $x$ for which $t$ is known `e.g., many movies for which we know the rating`.
- **A Model**: A function representing the relationship between $x$ and $t$.
- **A Loss or a Cost or an Objective Function**: Determines how well our model approximates the training examples.
- **Optimization**: A method of finding the parameters of our model that minimizes the loss function.
## 📊 What is Regression?

- Regression is a statistical approach for modeling the relationship between some `variables` $x$ (features) and some real-valued `outcome` $y$.
	![[Regression.png]]
## Regression Types

- **Linear Regression**
- **Nonlinear Regression**
---
## Linear Regression

- Let’s say we have this dataset:

| Size (x) | Price (y) |
|----------|-----------|
| 100      | 50        |
| 150      | 100       |
| 200      | 150       |
| 250      | 200       |
| 300      | 250       |
![[dataset-1.png]]
### **Linear Function**
$$f(x) = \theta x + b$$
- $f(x) = model$ → $y$
- $x$: variable (feature)
- $\theta$: coefficient (Slope)
- $b$: y-axis intercept (Bias)
#### Example

| x   | -1  | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- | --- |
| y   | -1  | 3   | 5   | 7   | 9   |
#### **Steps:**
1. Visualize
	![[Visualize-1.png]]
2. Find parameter $\theta$:
$$\large f(x)' = \theta = \frac{{y_2 - y_1}}{{x_2 - x_1}} = \frac{9 - 7}{4 - 3} = 2$$$$\int f(x)' = 2x + b$$
3. Find parameter $b$: 
$$\large b = y - \theta x = 7 - 2 \ x \ 3 = 1$$

4. model:
$$\large f(x) = 2x + 1$$
---
## Gradient Descent

**Equations:**
- $f(x) = \theta x + b$ `will be` $\large \rightarrow$ $h(x) = \theta_i x_i + \theta_0$

🎯 **Objective:**
- $y$ → Output/Target Value
- $(x, y)$ → Data Point/Training Example

**Model Representation:**
- $h(x)$ → Model
- $x_i$ → Feature
- $\theta_i x_i + \theta_0$ → Parameters/Weights

	![[Gradient Descent.png]]
### Adding a New Feature: Finding $\theta_0$, $\theta_1$, $\theta_2$

| Size | Room# | Price |
|------|-------|-------|
| 100  | 4     | 6000  |
| 130  | 5     | 7000  |
| 170  | 5     | 5000  |
| 190  | 6     | 9000  |
| 200  | 6     | 11000 |
![[New-Feature-1.png]]
#### Structure of Supervised Learning:

![[Supervised Learning 1.png]]
### Features Representation:
- n feathers $$h(x) = \theta_0 x_0 + \theta_1 x_1 + \theta_2 x_2 +...+ \theta_j x_j + $$
- Let's Simplify $$h(x) = \sum_{i=1}^{n} \theta_j x_j \quad\quad\quad \begin{matrix} n = \# of features \\ j = j^{th}, counter \end{matrix}$$$$ \theta =\begin{bmatrix}\theta_0 \\ \theta_1 \\ \theta_2 \\. \\ . \\ . \\ \theta_n \end{bmatrix} \quad\quad\quad x = \begin{bmatrix}x_0 \\ x_1 \\ x_2 \\. \\ . \\ . \\ x_n\end{bmatrix}$$
- Find $\theta_n$ values such that $h(x) \approx y$
#### Finding $\theta_n$:

| size | Room# | Price |
| ---- | ----- | ----- |
| 100  | 4     | 600   |
$h(x) = \theta_0 + \theta_1 \times 100 + \theta_2 \times 4$

+ **Initialization:** $\theta_n (\theta_0=50, \theta_1=50, \theta_2=100)$
- So, $h(x) = 5450$
Calculate the squared difference between actual value $y$ and predicted value $h(x)$: $(h(x) - y)^2 = (5450 - 6000)^2 = 302500$ $\rightarrow$ $min(h(x) - y)^2$

## Least Squares Error

- The "best fit" means the difference between actual $y$ values and predicted values are a minimum. $min(h(x) - y)^2$
- ![[Least Squares.png]]
- $\text{Sum of Squared errors (Differences) SSE}:$
$$SSE = \sum_{i=1}^{m} (h(x^{(i)}) - y^{(i)})^2$$
- $\text{Sum of Squared Errors (Residual) SSE}:$
$$SSE = \sum_{i=1}^{m} (h(x^{(i)}) - y^{(i)})^2$$
- $\text{Least Squares (LS) minimizes the Sum of Squared errors}:$
$$LS = \min \sum_{i=1}^{m} (h(x^{(i)}) - y^{(i)})^2$$
- $\text{Least Squares (LS) minimizes the Sum of Squared errors}:$
$$LS = \min \sum_{i=1}^{m} (h(x^{(i)}) - y^{(i)})^2$$

- How we can calculate the minimum:
	- Mean Absolute Error (MAE)
	- Root Mean Squared Error (RMSE)
	- Relative Absolute Error (RAE)

- Least Squares (LS):
$$LS = \min \sum_{i=1}^{m} (h(x^{(i)}) - y^{(i)})^2$$
	- This cost function is called Ordinary Least Squares and is defined as follows:
$$J(\theta) = \frac{1}{2m} \sum_{i=1}^{m} (h(x^{(i)}) - y^{(i)})^2$$
The goal of learning is to minimize the cost function $J(\theta)$.
