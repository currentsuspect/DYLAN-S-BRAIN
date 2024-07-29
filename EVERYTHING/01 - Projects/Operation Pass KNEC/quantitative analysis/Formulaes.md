Certainly! Here's a summary of key formulas and concepts from the topics we've covered so far, focusing on those essential for your Quantitative Methods exam preparation:

### **1. Measures of Central Tendency**
- **Mode (Grouped Data):**
  \[
  \text{Mode} = L + \left( \frac{f_m - f_1}{2f_m - f_1 - f_2} \right) \times h
  \]
  where:
  - \( L \) = lower class boundary of the modal class
  - \( f_m \) = frequency of the modal class
  - \( f_1 \) = frequency of the class preceding the modal class
  - \( f_2 \) = frequency of the class succeeding the modal class
  - \( h \) = class width

- **Median (Grouped Data):**
  \[
  \text{Median} = L + \left( \frac{\frac{N}{2} - CF}{f} \right) \times h
  \]
  where:
  - \( L \) = lower class boundary of the median class
  - \( N \) = total number of observations
  - \( CF \) = cumulative frequency of the class before the median class
  - \( f \) = frequency of the median class
  - \( h \) = class width

- **Mean (Grouped Data):**
  \[
  \text{Mean} = \frac{\sum f_i x_i}{\sum f_i}
  \]
  where:
  - \( f_i \) = frequency of the \( i \)-th class
  - \( x_i \) = midpoint of the \( i \)-th class

### **2. Measures of Dispersion**
- **Variance (Grouped Data):**
  \[
  s^2 = \frac{\sum f_i (x_i - \bar{x})^2}{\sum f_i}
  \]
  where:
  - \( \bar{x} \) = mean of the data
  - \( f_i \) = frequency of the \( i \)-th class
  - \( x_i \) = midpoint of the \( i \)-th class

- **Standard Deviation:**
  \[
  s = \sqrt{\frac{\sum f_i (x_i - \bar{x})^2}{\sum f_i}}
  \]

- **Quartile Deviation (Interquartile Range):**
  \[
  QD = \frac{Q_3 - Q_1}{2}
  \]
  where:
  - \( Q_1 \) = First quartile
  - \( Q_3 \) = Third quartile

- **Coefficient of Quartile Deviation:**
  \[
  CQD = \frac{Q_3 - Q_1}{Q_3 + Q_1}
  \]

### **3. Sampling and Standard Error**
- **Standard Error of the Mean:**
  \[
  SE = \frac{\sigma}{\sqrt{n}}
  \]
  where:
  - \( \sigma \) = population standard deviation
  - \( n \) = sample size

### **4. Confidence Intervals**
- **Confidence Interval for Population Mean (Large Sample):**
  \[
  \bar{x} \pm Z \left( \frac{\sigma}{\sqrt{n}} \right)
  \]
  where:
  - \( \bar{x} \) = sample mean
  - \( Z \) = Z-value corresponding to the confidence level
  - \( \sigma \) = population standard deviation
  - \( n \) = sample size

- **Confidence Interval for Population Mean (Small Sample):**
  \[
  \bar{x} \pm t \left( \frac{s}{\sqrt{n}} \right)
  \]
  where:
  - \( \bar{x} \) = sample mean
  - \( t \) = t-value corresponding to the confidence level and degrees of freedom
  - \( s \) = sample standard deviation
  - \( n \) = sample size

### **5. Correlation and Regression**
- **Pearson Correlation Coefficient:**
  \[
  r = \frac{n \sum xy - (\sum x)(\sum y)}{\sqrt{[n \sum x^2 - (\sum x)^2][n \sum y^2 - (\sum y)^2]}}
  \]

- **Spearman's Rank Correlation Coefficient:**
  \[
  r_s = 1 - \frac{6 \sum d_i^2}{n(n^2 - 1)}
  \]
  where:
  - \( d_i \) = difference between the ranks of each observation
  - \( n \) = number of observations

### **6. Linear Programming**
- **General Formulation:**
  Maximize or Minimize \( Z = c_1x_1 + c_2x_2 + \ldots + c_nx_n \)
  Subject to:
  \[
  \begin{aligned}
    & a_{11}x_1 + a_{12}x_2 + \ldots + a_{1n}x_n \le b_1 \\
    & a_{21}x_1 + a_{22}x_2 + \ldots + a_{2n}x_n \le b_2 \\
    & \ldots \\
    & a_{m1}x_1 + a_{m2}x_2 + \ldots + a_{mn}x_n \le b_m \\
    & x_1, x_2, \ldots, x_n \ge 0
  \end{aligned}
  \]

### **7. Monte Carlo Simulation**
- **Random Sample Generation:**
  - \( X_i \sim \mathcal{N}(\mu, \sigma^2) \) for normal distribution
  - \( X_i \sim U(a, b) \) for uniform distribution

### **8. Network Planning**
- **Critical Path Method (CPM):**
  - Calculate earliest start (ES) and latest start (LS) times for each task.
  - Identify the critical path by tasks with zero slack time.

### **9. Simulation**
- **Basic Monte Carlo Steps:**
  1. Define the problem.
  2. Specify input probability distributions.
  3. Generate random samples.
  4. Perform simulation runs.
  5. Analyze results.

### Common Confidence Levels

| Confidence Level | Z-Value   | t-Value (Example, df=9) |
|------------------|-----------|-------------------------|
| 90%              | 1.645     | 1.833                   |
| 95%              | 1.960     | 2.262                   |
| 99%              | 2.576     | 3.250                   |

Feel free to ask for more examples or any additional explanations on specific topics!