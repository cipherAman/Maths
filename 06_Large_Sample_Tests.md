# 6. Tests for Large Samples ($n \ge 30$)

When the sample size is large (typically $n \ge 30$), the sample distribution of the statistic is approximately normal, according to the Central Limit Theorem. We use the **Z-test** for large samples.

The general formula for the test statistic $Z$ is:
$$ Z = \frac{\text{Statistic} - \text{Parameter}}{\text{Standard Error of the Statistic}} $$

---

## 6.1 Test for Single Mean
This test determines if a sample mean significantly differs from a hypothesized population mean.

**Hypotheses:**
- $H_0: \mu = \mu_0$
- $H_1: \mu \neq \mu_0$ (Two-tailed) or $\mu > \mu_0$ (Right-tailed) or $\mu < \mu_0$ (Left-tailed)

**Test Statistic:**
$$ Z = \frac{\bar{x} - \mu_0}{\frac{\sigma}{\sqrt{n}}} $$
Where:
- $\bar{x}$ = Sample mean
- $\mu_0$ = Hypothesized population mean
- $\sigma$ = Population standard deviation (if unknown, use sample standard deviation $s$)
- $n$ = Sample size

---

## 6.2 Test for Difference of Means
This test determines if there is a significant difference between the means of two independent large samples.

**Hypotheses:**
- $H_0: \mu_1 = \mu_2$ (or $\mu_1 - \mu_2 = 0$)
- $H_1: \mu_1 \neq \mu_2$ (Two-tailed) or $\mu_1 > \mu_2$ or $\mu_1 < \mu_2$ (One-tailed)

**Test Statistic:**
$$ Z = \frac{(\bar{x}_1 - \bar{x}_2) - (\mu_1 - \mu_2)}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}} $$
Under $H_0$, we assume $\mu_1 - \mu_2 = 0$:
$$ Z = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}} $$
*(If population standard deviations $\sigma_1, \sigma_2$ are unknown, use sample standard deviations $s_1, s_2$.)*

---

## 6.3 Test for Single Proportion
This test determines if a sample proportion significantly differs from a hypothesized population proportion. We define a "success" and a "failure".

**Hypotheses:**
- $H_0: P = P_0$
- $H_1: P \neq P_0$ (Two-tailed) or $P > P_0$ or $P < P_0$ (One-tailed)

**Test Statistic:**
$$ Z = \frac{p - P_0}{\sqrt{\frac{P_0 Q_0}{n}}} $$
Where:
- $p = \frac{x}{n}$ = Sample proportion ($x$ is the number of successes in sample size $n$)
- $P_0$ = Hypothesized population proportion
- $Q_0 = 1 - P_0$
- $n$ = Sample size

---

## 6.4 Test for Difference of Proportions
This test determines if there is a significant difference between the proportions of successes in two independent large samples.

**Hypotheses:**
- $H_0: P_1 = P_2$
- $H_1: P_1 \neq P_2$ (Two-tailed) or $P_1 > P_2$ or $P_1 < P_2$ (One-tailed)

**Test Statistic:**
$$ Z = \frac{p_1 - p_2}{\sqrt{P Q \left(\frac{1}{n_1} + \frac{1}{n_2}\right)}} $$
Where:
- $p_1 = \frac{x_1}{n_1}$, $p_2 = \frac{x_2}{n_2}$ are the sample proportions.
- $P$ is the pooled estimate of the population proportion under $H_0$:
  $$ P = \frac{x_1 + x_2}{n_1 + n_2} = \frac{n_1 p_1 + n_2 p_2}{n_1 + n_2} $$
- $Q = 1 - P$
