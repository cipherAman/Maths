# 7. Tests for Small Samples ($n < 30$)

When the sample size is small ($n < 30$), the sampling distribution of the test statistic is not necessarily normal. If the population itself is known or assumed to be normally distributed, we use Student's t-test, F-test, or Chi-square test depending on the parameters being tested.

---

## 7.1 Student's t-test for Single Mean
This test determines if a sample mean significantly differs from a hypothesized population mean when the population standard deviation ($\sigma$) is unknown and the sample size is small.

**Assumptions:** Parent population is normal, sample is small ($n < 30$), population variance is unknown.

**Test Statistic:**
$$ t = \frac{\bar{x} - \mu}{\frac{s}{\sqrt{n}}} $$
Where:
- $\bar{x}$ = Sample mean
- $\mu$ = Hypothesized population mean
- $n$ = Sample size
- $s$ = Sample standard deviation, defined as $s^2 = \frac{\sum (x_i - \bar{x})^2}{n - 1}$
- **Degrees of Freedom ($v$):** $v = n - 1$. We compare the calculated $|t|$ value with the tabulated $t$-value for $v$ degrees of freedom at the chosen level of significance ($\alpha$).

---

## 7.2 Student's t-test for Difference of Means
This test determines if there is a significant difference between the means of two independent small samples.

**Assumptions:** Parent populations are normal, sample sizes are small ($n_1 < 30, n_2 < 30$), population variances are unknown but assumed to be equal ($\sigma_1^2 = \sigma_2^2$).

**Test Statistic:**
$$ t = \frac{(\bar{x}_1 - \bar{x}_2)}{\sqrt{S^2 \left(\frac{1}{n_1} + \frac{1}{n_2}\right)}} $$
Where:
- $\bar{x}_1, \bar{x}_2$ = Sample means
- $n_1, n_2$ = Sample sizes
- $S^2$ is the pooled estimator of the common population variance:
  $$ S^2 = \frac{\sum (x_i - \bar{x}_1)^2 + \sum (y_i - \bar{x}_2)^2}{n_1 + n_2 - 2} = \frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2} $$
- **Degrees of Freedom ($v$):** $v = n_1 + n_2 - 2$

---

## 7.3 F-test for Comparison of Variances
The F-test is used to test whether there is a significant difference between the variances of two independent normal populations based on two small samples.

**Hypotheses:**
- $H_0: \sigma_1^2 = \sigma_2^2$
- $H_1: \sigma_1^2 \neq \sigma_2^2$ (Two-tailed test)

**Test Statistic:**
$$ F = \frac{S_1^2}{S_2^2} $$
Where:
- We place the larger variance in the numerator so that $F \ge 1$. Let's assume $S_1^2 > S_2^2$.
- $S_1^2 = \frac{\sum (x_i - \bar{x})^2}{n_1 - 1}$ and $S_2^2 = \frac{\sum (y_i - \bar{y})^2}{n_2 - 1}$ are the unbiased estimates of the population variances.
- **Degrees of Freedom:** $v_1 = n_1 - 1$ (numerator df) and $v_2 = n_2 - 1$ (denominator df).

If the calculated $F$ is greater than the tabulated value $F_{\alpha}(v_1, v_2)$, we reject the null hypothesis.

---

## 7.4 Chi-square Test for Goodness of Fit ($\chi^2$)
This test is used to determine how well an observed frequency distribution matches an expected (theoretical) frequency distribution.

**Hypotheses:**
- $H_0$: There is no significant difference between the observed and expected frequencies (i.e., the data follows the expected distribution).
- $H_1$: There is a significant difference.

**Test Statistic:**
$$ \chi^2 = \sum \frac{(O_i - E_i)^2}{E_i} $$
Where:
- $O_i$ = Observed frequency in the $i$-th class/category
- $E_i$ = Expected frequency in the $i$-th class/category
- **Degrees of Freedom ($v$):** $v = n - 1$ (where $n$ is the number of classes/categories). If parameters of the expected distribution are estimated from the data, we subtract $1$ more degree of freedom for each estimated parameter (e.g., $v = n - 1 - k$).

**Conditions for Chi-square Test:**
1. The observations must be independent.
2. The total frequency $N$ ($\sum O_i$) should be reasonably large (usually $\ge 50$).
3. No expected cell frequency ($E_i$) should be extremely small (usually $E_i \ge 5$). If any $E_i < 5$, adjacent cells are combined to make the expected frequency sum to at least 5.
