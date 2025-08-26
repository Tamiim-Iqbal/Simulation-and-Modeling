<h1 align="center">Simulation & Modeling</h1>

<h2>Contents </h2>

- [t-Test](#t-test)
- [Two-Sample t-Test](#two-sample-t-test)
  
---

### t-Test

<h4> Hypothesis </h4>

A **hypothesis** is just a guess or assumption about something. <br>
Example: <br>
You think drinking coffee before studying improves test scores.
This is your **hypothesis—something you want to test.**

<h4> Null Hypothesis </h4>

- H_o says “Nothing special is happening”. It assumes no effect or no difference. 
- “Drinking coffee does not improve test scores” 
- It means coffee has no real effect, and any difference in scores is just by chance.

<h4>Alternative Hypothesis </h4>

- H_1 says something is happening – There is a difference or effect. 
- “Drinking coffee improves test scores”. 
- It means coffee actually makes a difference in performance.

<h4>What is a t-Test?</h4>

- A statistical test to compare a sample mean to a known value.
- Example: A fitness app claims users walk 10,000 steps per day on average. You collect data from 50 users and perform a t-test to see if the claim is accurate.

<h4>Why use t-test? </h4>

- Imagine you own a coffee shop. 
- You claim that the average customer spends TK 500 per visit. 
- To verify this claim, you collect data from 30 customers.
- Perform a one-sample t-test to check if your claim holds true.

<h4>One-Sample T-Test </h4>

- Compare a sample to a known value.
- Imagine you are in a math class where the teacher says that the average exam score for all students in the school is 70 out of 100.
- You want to check if your class (a sample of students) has an average score different from 70.
- To do this, you take the scores of 10 students from your class and perform a one-sample t-test.

<h4>Real life example  </h4> 

- Imagine your teacher says the average test score in the school is 70. (Assumption on population)
- You test 10 students from your class to see if your class is different.
- **H_0 (Null Hypothesis):** Your class has the same average score as the school [sample mean equals the population mean (μ=μ0​).]

- **H_1 (Alternative Hypothesis):** Your class has a different average score than your school (not 70) **[The sample mean does not equal the population mean (μ≠μ0) for a two-tailed test.]**

<h4> Two-tailed Test </h4> 

- Check if a value is different in either direction (higher or lower) compared to a given value (here, mean)
- H_1: 70≠μ0
- H_0: 70=μ0
- Your class average is 80, reject H_0
- class average is 60, reject H_0
- 71 or 69 ? Fail to reject H_0

<h4>T-Test Formula</h4> 

The t-test formula is:

$$
t = \frac{\bar{x} - \mu_0}{s / \sqrt{n}}
$$
**Where:**
- $t$ = t-statistic (a number that tells us how far our sample mean is from the population mean in terms of standard errors)
- $\bar{x}$ = sample mean (average of your sample data)
- $\mu_0$ = Hypothesized population mean (the value you are comparing your sample to)
- $s$ = sample standard deviation (how much your sample data varies)
- $n$ = sample size (number of observations in your sample)

<h4>Steps to Perform a One-Sample t-Test in Python</h4> 

- Claim: The teacher says the average exam score **in the school is 70**
- Step 1: Collect Data 
  - Let's assume these are the exam scores of 10 students **in your class:**
[65, 72, 68, 75, 80, 62, 71, 78, 74, 69]. You want to check if the average score is **significantly different from 70** using one-sample t-test
- Step 2: Define Hypotheses 
  - Null Hypothesis (H₀): The average class score is equal to 70.
  - Alternative Hypothesis (H₁): The average class score is not equal to 70.

<h4>Significance Level (α) </h4> 

- The probability of rejecting the null hypothesis when it is actually true.
- It represents the risk of making Type I error (False Positive)
- α = 0.05 (Means we accept a 5% chance of wrongly concluding that the class’s average is not 70 when it is actually 70 (equal to population’s mean))

<h4>P-value</h4>

- The p-value tells us the probability of getting a result this far from 70, just by chance.
- If the p-value is less than α, reject H0​.
- Lower p-value means stronger evidence against H_0
- Higher p-value means not enough evidence to reject H_0

<h4>Degrees of Freedom</h4> 

- The number of data points that are free to vary
- In one-sample t-test, usually, df = n-1, where n is sample size
- You need mean to calculate, so you assume mean should not get the freedom to vary (assuming mean is in data point)

<h4>Assumptions</h4> 

- Data is continuous.
- Data follows a normal distribution.
- Sample observations are independent

<h4> Code </h4> 
- [05_t_Test.ipynb](https://github.com/Tamiim-Iqbal/Simulation-and-Modeling/blob/main/05_t_Test.ipynb)

<h4> t_Test_Assignment </h4>

- [06_t_Test_Assignment.ipynb](https://github.com/Tamiim-Iqbal/Simulation-and-Modeling/blob/main/06_t_Test_Assignment.ipynb)


### Two-Sample t-Test

- The two-sample t-test determines whether the means of two independent samples are significantly different.

<h4> Types: </h4>
  
1. Equal Variance (Pooled t-test)
2. Unequal Variance (Welch's t-test)

<h4>Equal Variance t-test (Pooled t-test)</h4>

- The pooled t-test assumes that the two groups have the same variance (homogeneity of variance). It pools the variances from both samples to estimate a common variance.

<h4>Pooled t-Test Formula </h4>
The t-test formula is:

$$
t = \frac{\bar{X}_1 - \bar{X}_2}{\sqrt{s_p^2 \left(\frac{1}{n_1} + \frac{1}{n_2}\right)}}
$$
$$
s_p^2 = \frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2}
$$

**Where:**
- $t$ = t-statistic (a number that tells us how far our sample means are from each other in terms of standard errors)
- $\bar{X}_1$ = mean of sample 1 (average of your first sample data)
- $\bar{X}_2$ = mean of sample 2 (average of your second sample data)
- $s_p^2$ = pooled variance (a combined measure of variability from both samples)
- $n_1$ = sample size of sample 1 (number of observations in your first sample)
- $n_2$ = sample size of sample 2 (number of observations in your second sample)
- $s_1^2$ = variance of sample 1 (how much your first sample data varies)
- $s_2^2$ = variance of sample 2 (how much your second sample data varies)

<h4>Example: Testing Exam Scores of Two Classes</h4>

- Suppose we compare the exam scores of Class A and Class B, assuming their performance variability is similar.
- Class A scores: [85, 90, 88, 92, 87, 89, 91, 86, 90, 88]
- Class B scores: [78, 82, 80, 79, 81, 83, 77, 82, 80, 79]
- We assume equal variance and apply the pooled t-test.

<h4>Unequal Variance t-test (Welch's t-test)</h4>

- The Welch's t-test is used when the two groups do not have the same variance. It is more flexible and does not assume equal variances.
- More robust for real-world data

<h4>Example: Comparing Heights of Two Groups</h4>

Suppose we want to compare the average height of **male** and **female** students in a school.  
Since **height variance may differ between genders**, we use **Welch’s t-test**.

- **Male heights (cm):** [170, 172, 175, 168, 174, 177, 180, 173, 169, 176]  
- **Female heights (cm):** [160, 162, 158, 165, 161, 164, 159, 163, 157, 166]  

Since their variances are likely **unequal**, Welch’s t-test is applied.


<h4>Key Assumptions</h4>

- The two samples are independent.
- The data in each group are normally distributed 
- The variances of the two groups are equal (for the standard t-test) or unequal (for the Welch's t-test).

<h4> Hypothesis Testing Framework </h4>

- Null Hypothesis (H0): The means of the two samples are equal (μ1 = μ2)
- Alternative Hypothesis (H1): The means are not equal (μ1 ≠ μ2)
- Significance Level (α): Commonly set to 0.05

<h4> Degrees of Freedom (df) in the Two-Sample t-Test</h4>

- Degrees of freedom (df) represent the number of independent values that can vary in a statistical calculation. In the context of the two-sample t-test, df helps determine the shape of the t-distribution used to calculate the p-value.
- The calculation of degrees of freedom differs between the Equal Variance (Pooled t-test) and Unequal Variance (Welch’s t-test).

For the **Unequal Variance (Welch’s t-test)**, the **degrees of freedom are not fixed** but are estimated  
using the **Welch–Satterthwaite equation**:

$$
df = \frac{\left( \frac{s_1^2}{n_1} + \frac{s_2^2}{n_2} \right)^2}
{\frac{\left( \frac{s_1^2}{n_1} \right)^2}{n_1 - 1} + \frac{\left( \frac{s_2^2}{n_2} \right)^2}{n_2 - 1}}
$$

**where:** 

- $s_1^2, s_2^2$ are the sample variances  
- $n_1, n_2$  are the sample sizes  

<h4>Working Procedure</h4>

1. Define H0 and H1
2. Collect and define two independent datasets
3. Specify variance assumption (equal/unequal)
4. Perform the t-test using Python
5. Interpret results (t-statistic, p-value, confidence interval)

<h4>Example: Testing the Effectiveness of a New Drug</h4>

- Scenario:
A pharmaceutical company wants to test whether a new drug (Drug A) is more effective in reducing blood pressure compared to a Amdocol Plus 50 (Drug B).

  - Group 1 (Drug A group): 10 patients took Drug A, and their blood pressure was measured.
  - Group 2 (Amdocol Plus 50 group): 10 different patients took Amdocol plus 50, and their blood pressure was also measured.
  
- Collected Data (Systolic Blood Pressure after Treatment):
  - Drug A group: [120, 115, 118, 122, 119, 117, 116, 121, 120, 118]
  - Amdocol group: [130, 128, 132, 135, 129, 127, 126, 134, 133, 131]

- Step 1: State the Hypotheses
  - Null Hypothesis (H₀): There is no difference in the mean blood pressure reduction between the two groups. (μ₁ = μ₂)
  - Alternative Hypothesis (H₁): There is a significant difference in the mean blood pressure reduction between the two groups. (μ₁ ≠ μ₂)

- Step 2: Perform the Two-Sample t-test

  The test statistic is calculated using:

  $$
  t = \frac{\bar{X}_1 - \bar{X}_2}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}}
  $$

  where:


  - $\bar{X}_1, \bar{X}_2$ are the sample means of Drug A and Amdocol   groups.  
  - $s_1^2, s_2^2$ are the sample variances.  
  - $n_1, n_2$ are the sample sizes.
- Step 3: Interpret the Results
  - If the **p-value** from the test is **less than** the significance level (usually 0.05), we **reject the null hypothesis**, meaning there is a significant difference in mean blood pressure reduction between Drug A and the placebo.
  - If the **p-value** is **greater than** 0.05, we **fail to reject the null hypothesis**, meaning there is no significant difference between the two groups.
  
<h4>Results</h4>

- Results of the Two-Sample t-Test
t-statistic= -10.02
p-value = 8.64 × 10⁻⁹ (very small)

**Interpretation** <br>
- Since the p-value is much smaller than the common significance level (0.05), we reject the null hypothesis (H₀). This means there is a statistically significant difference between the mean blood pressure levels of the Drug A group and the Amdocol group. 

- In simpler terms, **Drug A has a significant effect in lowering blood pressure compared to the Amdocol**.
- p-Value < 0.05 → Reject H0 (Significant difference in means)
- p-Value ≥ 0.05 → Fail to reject H0 (No significant difference)
- Confidence interval helps assess the mean difference

<h4>Conclusion of Scenario</h4>

- If the test results show a significant difference, the company can conclude that Drug A is effective in reducing blood pressure compared to the Amdocol. 
- If not, there is no strong statistical evidence to support the claim that Drug A is better.

<h4>Confidence Interval (CI): Estimating the True Difference</h4>

- The confidence interval (CI) gives us a range of values where we expect the true difference in means to lie.
- If the CI includes 0 → The difference is not statistically significant.
- If the CI does not include 0 → The difference is statistically significant.

<h4>Variances: Why We Used the Unequal Variance t-Test (Welch’s t-Test)</h4>

- Variance measures how much the data points in each group spread out from the mean.
- If the two groups have very different variances, the standard t-test may not be reliable.
- Welch’s t-test is more robust and does not assume equal variances.

<h4>Importance of Choosing the Right t-Test</h4>

- This experiment shows that choosing the correct version of the t-test is essential.
- If variances are equal, we use the pooled t-test (Student’s t-test).
- If variances are unequal, we use Welch’s t-test.
- Interpreting the p-value and confidence interval helps in decision-making.

<h4>Conclusion</h4>

- The two-sample t-test is a powerful method to compare means of two independent samples. Understanding variance assumptions and interpreting results correctly is crucial for data-driven decision-making.