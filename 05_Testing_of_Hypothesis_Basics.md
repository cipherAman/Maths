# 5. Basics of Hypothesis Testing

## 5.1 Introduction to Hypothesis Testing

**Hypothesis Testing** is a formal procedure used by statisticians to accept or reject statistical hypotheses. The primary goal is to determine if there is enough evidence in a sample of data to infer that a certain condition holds true for the entire population.

## 5.2 Null and Alternative Hypothesis

1. **Null Hypothesis ($H_0$):**
   The null hypothesis is the statement of "no difference", "no effect", or "status quo". It is the hypothesis that the researcher is trying to disprove or reject. We usually start by assuming the null hypothesis is true until evidence indicates otherwise.
   *Example:* A coin is fair ($P(Heads) = 0.5$). The new drug has no effect on blood pressure.

2. **Alternative Hypothesis ($H_1$ or $H_a$):**
   The alternative hypothesis is the statement that contradicts the null hypothesis. It represents what the researcher is trying to prove or what they suspect is actually true.
   *Example:* The coin is biased ($P(Heads) \neq 0.5$). The new drug lowers blood pressure.

## 5.3 Types of Errors

When making a decision in hypothesis testing, there are two possible types of errors:
- **Type I Error ($\alpha$):** Rejecting the null hypothesis when it is actually true. (False Positive). The probability of a Type I error is the level of significance ($\alpha$).
- **Type II Error ($\beta$):** Failing to reject the null hypothesis when the alternative hypothesis is true. (False Negative).

## 5.4 Level of Significance ($\alpha$)

The **Level of Significance**, denoted by $\alpha$, is the maximum acceptable probability of making a Type I error. It is the threshold set by the researcher before the test begins.
- Common values for $\alpha$ are $0.05$ (5%), $0.01$ (1%), and $0.10$ (10%).
- If $\alpha = 0.05$, it means there is a 5% risk of concluding that a difference exists when there is no actual difference.

## 5.5 Critical Region and Test Statistic

- **Test Statistic:** A standardized value calculated from sample data during a hypothesis test. You use it to decide whether to reject the null hypothesis. Examples include the Z-statistic (for large samples) and the t-statistic (for small samples).
- **Critical Region (Rejection Region):** The set of values for the test statistic that leads to the rejection of the null hypothesis. It is determined by the level of significance $\alpha$.

## 5.6 One-Tailed and Two-Tailed Tests

The direction of the alternative hypothesis determines whether the test is one-tailed or two-tailed.

1. **Two-Tailed Test (Non-Directional):**
   Used when we want to test if a parameter is significantly different from a hypothesized value, in *either* direction (greater than or less than).
   - $H_0: \mu = \mu_0$
   - $H_1: \mu \neq \mu_0$
   - The critical region is split equally between the two tails of the distribution (each tail has area $\alpha/2$).

2. **One-Tailed Test (Directional):**
   Used when we are interested in a specific direction of the difference.

   - **Right-Tailed Test (Upper Tail):**
     - $H_0: \mu \le \mu_0$ (or simply $\mu = \mu_0$)
     - $H_1: \mu > \mu_0$
     - The entire critical region ($\alpha$) is in the right tail.

   - **Left-Tailed Test (Lower Tail):**
     - $H_0: \mu \ge \mu_0$ (or simply $\mu = \mu_0$)
     - $H_1: \mu < \mu_0$
     - The entire critical region ($\alpha$) is in the left tail.

## 5.7 Steps in Hypothesis Testing
1. State the Null ($H_0$) and Alternative ($H_1$) hypotheses.
2. Choose the level of significance ($\alpha$).
3. Identify the appropriate test statistic and find its distribution (Z, t, Chi-square, F).
4. Determine the critical region based on $\alpha$ and the type of test (1-tailed or 2-tailed).
5. Compute the value of the test statistic from the sample data.
6. Make a Decision: Reject $H_0$ if the test statistic falls in the critical region; otherwise, do not reject $H_0$.
