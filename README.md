<h1 align="center">Simulation & Modeling</h1>

<h2>Contents </h2>

- [05: t-Test](#05-t-test)
  - [Hypothesis](#hypothesis)
  - [Null Hypothesis](#null-hypothesis)
  - [Alternative Hypothesis](#alternative-hypothesis)
  - [What is a t-Test?](#what-is-a-t-test)
  - [Why use t-test?](#why-use-t-test)
  - [One-Sample T-Test](#one-sample-t-test)
  - [Real life example](#real-life-example)
  - [Two-tailed Test](#two-tailed-test)
  - [T-Test Formula](#t-test-formula)
  - [Steps to Perform a One-Sample t-Test in Python](#steps-to-perform-a-one-sample-t-test-in-python)
  - [Significance Level (α)](#significance-level-α)
  - [P-value](#p-value)
  - [Degrees of Freedom](#degrees-of-freedom)
  - [Assumptions](#assumptions)
  - [Code](#code)
- [06: t-Test Assignment](#06-t-test-assignment)
  


## 05: t-Test

### Hypothesis 
- A **hypothesis** is just a guess or assumption about something. <br>
Example: <br>
You think drinking coffee before studying improves test scores.
This is your **hypothesis—something you want to test.**

### Null Hypothesis
- H_o says “Nothing special is happening”. It assumes no effect or no difference. 
- “Drinking coffee does not improve test scores” 
- It means coffee has no real effect, and any difference in scores is just by chance.

### Alternative Hypothesis
- H_1 says something is happening – There is a difference or effect. 
- “Drinking coffee improves test scores”. 
- It means coffee actually makes a difference in performance.

### What is a t-Test?
- A statistical test to compare a sample mean to a known value.
- Example: A fitness app claims users walk 10,000 steps per day on average. You collect data from 50 users and perform a t-test to see if the claim is accurate.

### Why use t-test?
- Imagine you own a coffee shop. 
- You claim that the average customer spends TK 500 per visit. 
- To verify this claim, you collect data from 30 customers.
- Perform a one-sample t-test to check if your claim holds true.

### One-Sample T-Test
- Compare a sample to a known value.
- Imagine you are in a math class where the teacher says that the average exam score for all students in the school is 70 out of 100.
- You want to check if your class (a sample of students) has an average score different from 70.
- To do this, you take the scores of 10 students from your class and perform a one-sample t-test.

### Real life example 
- Imagine your teacher says the average test score in the school is 70. (Assumption on population)
- You test 10 students from your class to see if your class is different.
- **H_0 (Null Hypothesis):** Your class has the same average score as the school [sample mean equals the population mean (μ=μ0​).]

- **H_1 (Alternative Hypothesis):** Your class has a different average score than your school (not 70) **[The sample mean does not equal the population mean (μ≠μ0) for a two-tailed test.]**

### Two-tailed Test
- Check if a value is different in either direction (higher or lower) compared to a given value (here, mean)
- H_1: 70≠μ0
- H_0: 70=μ0
- Your class average is 80, reject H_0
- class average is 60, reject H_0
- 71 or 69 ? Fail to reject H_0

### T-Test Formula
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

### Steps to Perform a One-Sample t-Test in Python
- Claim: The teacher says the average exam score **in the school is 70**
- Step 1: Collect Data 
  - Let's assume these are the exam scores of 10 students **in your class:**
[65, 72, 68, 75, 80, 62, 71, 78, 74, 69]. You want to check if the average score is **significantly different from 70** using one-sample t-test
- Step 2: Define Hypotheses 
  - Null Hypothesis (H₀): The average class score is equal to 70.
  - Alternative Hypothesis (H₁): The average class score is not equal to 70.

### Significance Level (α)
- The probability of rejecting the null hypothesis when it is actually true.
- It represents the risk of making Type I error (False Positive)
- α = 0.05 (Means we accept a 5% chance of wrongly concluding that the class’s average is not 70 when it is actually 70 (equal to population’s mean))

### P-value
- The p-value tells us the probability of getting a result this far from 70, just by chance.
- If the p-value is less than α, reject H0​.
- Lower p-value means stronger evidence against H_0
- Higher p-value means not enough evidence to reject H_0

### Degrees of Freedom
- The number of data points that are free to vary
- In one-sample t-test, usually, df = n-1, where n is sample size
- You need mean to calculate, so you assume mean should not get the freedom to vary (assuming mean is in data point)

### Assumptions
- Data is continuous.
- Data follows a normal distribution.
- Sample observations are independent

### Code 
- [Github](https://github.com/Tamiim-Iqbal/Simulation-and-Modeling/blob/main/05_t_Test.ipynb)
## 06: t-Test Assignment