### 1. **Understanding Correlation**
   - **Q:** Define the term correlation and explain the difference between positive and negative correlation.
?
   - **A:** Correlation measures the strength and direction of the linear relationship between two variables. Positive correlation indicates that as one variable increases, the other also increases. Negative correlation indicates that as one variable increases, the other decreases.



2. **Calculating Correlation Coefficient**
   - **Q:** Given the following data, calculate the Pearson correlation coefficient between variables X and Y:
     ```
     X: 10, 12, 14, 16, 18
     Y: 20, 24, 28, 32, 36
     ```
?   
   - **A:** The Pearson correlation coefficient \( r \) can be calculated using the formula for \( r \). (Provide detailed steps for calculation).



3. **Interpreting Correlation Coefficient**
   - **Q:** Interpret a correlation coefficient of 0.85 in the context of a study examining the relationship between hours studied and exam scores.
   - **A:** A correlation coefficient of 0.85 indicates a strong positive linear relationship between hours studied and exam scores, suggesting that as study hours increase, exam scores tend to increase as well.

### Regression Questions

1. **Understanding Regression**
   - **Q:** Explain the concept of simple linear regression and its purpose in statistical analysis.
   - **A:** Simple linear regression is used to model the relationship between a dependent variable and a single independent variable by fitting a linear equation to observed data. It helps predict the dependent variable based on the value of the independent variable.

2. **Regression Equation**
   - **Q:** Given the following data points, find the regression equation \( Y = a + bX \):
     ```
     X: 2, 4, 6, 8, 10
     Y: 3, 7, 11, 15, 19
     ```
   - **A:** Calculate the slope \( b \) and intercept \( a \) using the formulas:
     \[
     b = \frac{n(\sum XY) - (\sum X)(\sum Y)}{n(\sum X^2) - (\sum X)^2}
     \]
     \[
     a = \frac{\sum Y - b(\sum X)}{n}
     \]
     (Provide detailed steps for calculation).

3. **Using Regression Equation**
   - **Q:** Using the regression equation \( Y = 2 + 3X \), predict the value of Y when X is 5.
   - **A:** Substitute \( X = 5 \) into the regression equation to find \( Y \):
     \[
     Y = 2 + 3(5) = 2 + 15 = 17
     \]

4. **Coefficient of Determination**
   - **Q:** Define the coefficient of determination \( R^2 \) and explain its significance in regression analysis.
   - **A:** The coefficient of determination \( R^2 \) measures the proportion of the variance in the dependent variable that is predictable from the independent variable(s). It indicates the goodness of fit of the regression model.

Sure, here's a structured schema for your questions and answers:

**Q1: Draw a scatter diagram for the following data and comment on the type of correlation:**

```
X: 5, 7, 9, 10, 12
Y: 15, 18, 22, 25, 30
```

**A1:**
- **Scatter Diagram:** Plotting the points (5, 15), (7, 18), (9, 22), (10, 25), (12, 30) shows a clear positive correlation.
- **Type of Correlation:** The data exhibits a positive linear correlation, where as X increases, Y also increases.

**Q2: Explain the difference between simple and multiple regression analysis. Give examples where each would be applicable.**

**A2:**
- **Simple Regression Analysis:**
  - **Definition:** Analyzes the relationship between one independent variable (X) and one dependent variable (Y).
  - **Example:** Predicting house prices based solely on square footage. Here, square footage (X) predicts house price (Y).

- **Multiple Regression Analysis:**
  - **Definition:** Analyzes the relationship between multiple independent variables (X1, X2, etc.) and one dependent variable (Y).
  - **Example:** Predicting a student's GPA using variables like study hours per week, attendance record, and previous GPA. Here, study hours, attendance, and previous GPA collectively predict GPA (Y).

**Q3: Given the following set of data, calculate the regression line and use it to predict the dependent variable:**

```
X: 1, 2, 3, 4, 5
Y: 2, 3, 5, 7, 11
```

**A3:**
- **Regression Line Calculation:**
  - Mean of X (meanX) = 3, Mean of Y (meanY) = 5.6
  - Slope (b) = 1.691, Intercept (a) = 1.528
  - Regression line: Y = 1.528 + 1.691 * X

- **Prediction for X = 6:**
  - Y = 1.528 + 1.691 * 6 = 11.014

**Q4: Describe the assumptions underlying the linear regression model and discuss the potential consequences of violating these assumptions.**

**A4:**
- **Assumptions:**
  1. Linearity: Relationship between X and Y is linear.
  2. Independence: Observations are independent.
  3. Homoscedasticity: Residuals have constant variance.
  4. Normality: Residuals are normally distributed.
  5. No multicollinearity: Independent variables are not highly correlated.

- **Consequences of Violations:**
  - Non-linearity leads to biased estimates and invalid predictions.
  - Autocorrelation affects coefficient estimates.
  - Heteroscedasticity affects prediction intervals.
  - Non-normality invalidates statistical tests.
  - Multicollinearity leads to unstable coefficient estimates.

#QuantitativeTechniques
