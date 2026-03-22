# Similar Practice Questions: Probability and Statistics
*Based on B.Tech 3rd Semester Examination 2024 (NEP) Pattern*

---

## Question 1: Theoretical Derivations

**(a) Derive the mean and variance of the Poisson distribution.**

**Solution:**

The probability mass function of the Poisson distribution is:

$$P(X=x) = \frac{e^{-\lambda}\lambda^x}{x!}, \quad x=0, 1, 2, \dots$$

**Mean ($E[X]$):**

$$E[X] = \sum_{x=0}^{\infty} x P(x) = \sum_{x=1}^{\infty} x \frac{e^{-\lambda}\lambda^x}{x!} = \lambda e^{-\lambda} \sum_{x=1}^{\infty} \frac{\lambda^{x-1}}{(x-1)!} = \lambda e^{-\lambda} e^{\lambda} = \mathbf{\lambda}$$

**Variance ($Var(X)$):**

To find the variance, first find $E[X(X-1)]$.

$$E[X(X-1)] = \sum_{x=2}^{\infty} x(x-1) \frac{e^{-\lambda}\lambda^x}{x!} = \lambda^2 e^{-\lambda} \sum_{x=2}^{\infty} \frac{\lambda^{x-2}}{(x-2)!} = \lambda^2 e^{-\lambda}e^{\lambda} = \lambda^2$$

$$Var(X) = E[X(X-1)] + E[X] - (E[X])^2 = \lambda^2 + \lambda - \lambda^2 = \mathbf{\lambda}$$

---

**(b) Derive the mean and variance of a continuous Uniform distribution over $(a, b)$.**

**Solution:**

The Probability Density Function (PDF) is:

$$f(x) = \frac{1}{b-a} \quad \text{for } a < x < b, \text{ and } 0 \text{ otherwise.}$$

**Mean:** 

$$E[X] = \int_a^b x \frac{1}{b-a} dx = \frac{1}{b-a} \left[ \frac{x^2}{2} \right]_a^b = \frac{b^2 - a^2}{2(b-a)} = \mathbf{\frac{a+b}{2}}$$

**Variance:** 

$$E[X^2] = \int_a^b x^2 \frac{1}{b-a} dx = \frac{1}{b-a} \left[ \frac{x^3}{3} \right]_a^b = \frac{b^3 - a^3}{3(b-a)} = \frac{a^2 + ab + b^2}{3}$$

$$Var(X) = E[X^2] - (E[X])^2 = \frac{a^2 + ab + b^2}{3} - \left( \frac{a+b}{2} \right)^2$$
$$Var(X) = \frac{4a^2 + 4ab + 4b^2 - 3a^2 - 6ab - 3b^2}{12} = \mathbf{\frac{(b-a)^2}{12}}$$

---
---

## Question 2: Maximum Likelihood Estimator (MLE)

**Let $X_1, X_2, \ldots, X_n$ be a random sample from an exponential distribution with pdf $f(x; \lambda) = \lambda e^{-\lambda x}$ for $x \ge 0$. Find the Maximum Likelihood Estimator (MLE) of $\lambda$.**

**Solution:**

**Likelihood function:**
$$L(\lambda) = \prod_{i=1}^n f(x_i; \lambda) = \prod_{i=1}^n \lambda e^{-\lambda x_i} = \lambda^n e^{-\lambda \sum_{i=1}^n x_i}$$

**Log-likelihood function:**
$$\ln L(\lambda) = n \ln \lambda - \lambda \sum_{i=1}^n x_i$$

Differentiating with respect to $\lambda$ and equating to 0 to find the maximum:
$$\frac{d}{d\lambda} \ln L(\lambda) = \frac{n}{\lambda} - \sum_{i=1}^n x_i = 0$$
$$\hat{\lambda} = \frac{n}{\sum_{i=1}^n x_i} = \frac{1}{\bar{x}}$$

So, the MLE of $\lambda$ is $\mathbf{\frac{1}{\bar{X}}}$.

---
---

## Question 3: Function of a Random Variable

**Let $f(x) = \frac{1}{4}$ for $-2 < x < 2$, zero elsewhere, be the pdf of X. Find the pdf of $Y = |X|$.**

**Solution:**

The range of $X$ is $(-2, 2)$, so the range of $Y = |X|$ is $(0, 2)$.

For $0 < y < 2$, the Cumulative Distribution Function (CDF) of $Y$ is:
$$F_Y(y) = P(Y \le y) = P(|X| \le y) = P(-y \le X \le y)$$
$$F_Y(y) = \int_{-y}^y f(x) dx = \int_{-y}^y \frac{1}{4} dx = \frac{1}{4} [x]_{-y}^y = \frac{2y}{4} = \frac{y}{2}$$

The pdf of $Y$ is the derivative of the CDF with respect to $y$:
$$f_Y(y) = \frac{d}{dy} \left( \frac{y}{2} \right) = \mathbf{\frac{1}{2}}$$

So, the pdf of $Y$ is $f_Y(y) = \frac{1}{2}$ for $0 < y < 2$, and $0$ elsewhere.

---
---

## Question 4: Probability (Combinatorics)

**Four distinct integers are chosen randomly from the first 20 positive integers. What is the probability that their sum is odd?**

**Solution:**

The first 20 positive integers $\{1, 2, 3, \dots, 20\}$ contain 10 odd and 10 even numbers.

Total ways to pick 4 integers = $\binom{20}{4} = \frac{20 \times 19 \times 18 \times 17}{4 \times 3 \times 2 \times 1} = 4845$.

For the sum to be odd, we must pick an **odd number of odd integers**. Since we choose 4 integers in total, the number of odd integers chosen must be either 1 or 3.

- **(1 Odd, 3 Even):** $\binom{10}{1} \times \binom{10}{3} = 10 \times \frac{10 \times 9 \times 8}{3 \times 2} = 10 \times 120 = 1200$ ways.
- **(3 Odd, 1 Even):** $\binom{10}{3} \times \binom{10}{1} = 120 \times 10 = 1200$ ways.

Total favorable outcomes = $1200 + 1200 = 2400$.

Probability = $\frac{\text{Favorable Outcomes}}{\text{Total Outcomes}} = \frac{2400}{4845} = \frac{480}{969} \approx \mathbf{0.495}$.

---
---

## Question 5: Large Sample Hypothesis Testing (Z-Test)

**A machine produces steel tubes with a mean diameter of 2.50 inches and a standard deviation of 0.05 inches. A random sample of 50 tubes is selected, and the average diameter is found to be 2.52 inches. Can we conclude at the 5% significance level that the machine is producing tubes with a diameter different from 2.50 inches?**

**Solution:**

Population mean $\mu = 2.50$, Population standard deviation $\sigma = 0.05$.
Sample size $n = 50$, Sample mean $\bar{x} = 2.52$.

- $H_0: \mu = 2.50$
- $H_1: \mu \ne 2.50$ (Two-tailed test)

**Test statistic:**
$$Z = \frac{\bar{x} - \mu}{\sigma / \sqrt{n}} = \frac{2.52 - 2.50}{0.05 / \sqrt{50}} = \frac{0.02}{0.00707} \approx 2.83$$

At 5% significance level, critical $Z = \pm 1.96$.

**Decision:** Calculated $Z$ ($2.83$) > $1.96$, so it falls in the critical/rejection region.
**Conclusion:** Since we reject $H_0$, we conclude that the machine is producing tubes with a diameter significantly different from 2.50 inches.

---
---

## Question 6: Small Sample Hypothesis Testing (T-Test)

**A tire manufacturer claims that its tires have a mean life of 40,000 km. A random sample of 8 tires showed a mean life of 38,500 km with a sample standard deviation of 2,000 km. Test the manufacturer's claim at a 5% level of significance. (Given $t_{0.05, 7} = 2.365$ for two-tailed).**

**Solution:**

Claim $\mu = 40,000$. 
Sample $n = 8$, mean $\bar{x} = 38,500$, sample standard deviation $S = 2,000$.

- $H_0: \mu = 40,000$
- $H_1: \mu \ne 40,000$

**Test statistic:**
$$t = \frac{\bar{x} - \mu}{S / \sqrt{n}} = \frac{38,500 - 40,000}{2,000 / \sqrt{8}} = \frac{-1500}{2000 / 2.828} = \frac{-1500}{707.1} \approx -2.12$$

Degrees of freedom $v = n - 1 = 7$. Critical value $t = \pm 2.365$.

**Decision:** Since $|-2.12| < 2.365$, the test statistic does not fall in the critical region.
**Conclusion:** We fail to reject $H_0$. The manufacturer's claim is valid at the 5% level of significance.

---
---

## Question 7: Two-Sample T-Test

**Two classes were given a math test. Class A (10 students) had a mean score of 75 with a sample variance of 25. Class B (8 students) had a mean score of 70 with a sample variance of 30. Is there a significant difference in the performance of the two classes at the 5% level of significance? (Given $t_{0.05, 16} = 2.12$).**

**Solution:**

**Class A:** $n_1 = 10, \bar{x}_1 = 75, s_1^2 = 25$.
**Class B:** $n_2 = 8, \bar{x}_2 = 70, s_2^2 = 30$.

- $H_0: \mu_1 = \mu_2$
- $H_1: \mu_1 \ne \mu_2$

**Pooled variance $S^2$:**
$$S^2 = \frac{(n_1-1)s_1^2 + (n_2-1)s_2^2}{n_1 + n_2 - 2} = \frac{9(25) + 7(30)}{10 + 8 - 2} = \frac{225 + 210}{16} = \frac{435}{16} = 27.1875$$

Pooled standard deviation $S = \sqrt{27.1875} \approx 5.214$.

**Test statistic:**
$$t = \frac{\bar{x}_1 - \bar{x}_2}{S \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}} = \frac{75 - 70}{5.214 \sqrt{\frac{1}{10} + \frac{1}{8}}} = \frac{5}{5.214 \sqrt{0.225}} = \frac{5}{5.214(0.474)} = \frac{5}{2.471} \approx 2.023$$

Degrees of freedom $v = 16$. Critical value $t = 2.12$.

**Decision:** Since calculated $t = 2.023 < 2.12$, the calculated $t$ is less than the critical value.
**Conclusion:** We fail to reject $H_0$. There is no significant difference in the performance of the two classes.
