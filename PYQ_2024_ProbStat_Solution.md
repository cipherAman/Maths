# B.Tech. 3rd Semester Examination, 2024 (NEP)
**Subject:** Probability and Statistics (BSC-302)  
**University:** Jharkhand University of Technology, Ranchi

---

## Question 1. Choose the correct option:

**(i) The errors in a page on a book of 1000 pages follows which distribution?**

(a) Binomial  
(b) Poisson  
(c) Hypergeometric  
(d) Exponential  

**Answer:** (b) Poisson

*Explanation:* Poisson distribution is used to model the number of rare events occurring in a fixed interval of time or space (like errors per page in a large book).

---

**(ii) Which of the following is wrong?**

(a) P(A|B) = P(A ∩ B) / P(B)  
(b) P(A|B) = P(B|A)P(A) / P(B)  
(c) P(A|B) = P(B|A) / P(A)P(B)  
(d) P(A ∩ B) = P(B|A)P(A)  

**Answer:** (c) P(A|B) = P(B|A) / P(A)P(B)

*Explanation:* Option (c) is an incorrect formula. (a) is the standard conditional probability definition, (b) is Bayes' theorem, and (d) is the multiplication rule.

---

**(iii) A person has bought 5 out of 50 tickets in a lottery, in which two are to be declared winners. What is the probability that the person wins the lottery?**

(a) 48C5 / 50C5  
(b) 45C2 / 50C2  
(c) 1 - 48C5 / 50C5  
(d) 1 - 45C2 / 50C2  

**Answer:** (c) 1 - 48C5 / 50C5

*Explanation:* Winning the lottery implies getting at least one winning ticket.  
P(Winning) = 1 - P(Losing all 5 tickets).  
The probability of choosing all 5 tickets purely from the 48 losing tickets is $\frac{^{48}C_5}{^{50}C_5}$.

---

**(iv) A red and a blue dice are rolled together, what is the probability that the number on blue die is greater than that on the red die?**

(a) 4/12  
(b) 5/12  
(c) 6/12  
(d) 7/12  

**Answer:** (b) 5/12

*Explanation:* The total number of equally likely outcomes is 36.  
The number of favorable outcomes where (Blue > Red) are:
- Red=1: Blue=2,3,4,5,6 (5 outcomes)
- Red=2: Blue=3,4,5,6 (4 outcomes)
- Red=3: Blue=4,5,6 (3 outcomes)
- Red=4: Blue=5,6 (2 outcomes)
- Red=5: Blue=6 (1 outcome)

Total favorable outcomes = 5 + 4 + 3 + 2 + 1 = 15.  
Probability = $\frac{15}{36} = \frac{5}{12}$.

---

**(v) If the value of z is greater than $z_\alpha$ while testing of hypothesis, then**

(a) $H_0$ is accepted with significance level $\alpha$.  
(b) $H_0$ is accepted with confidence level $\alpha$.  
(c) $H_0$ is rejected with significance level $\alpha$.  
(d) $H_0$ is rejected with confidence level $\alpha$.  

**Answer:** (c) $H_0$ is rejected with significance level $\alpha$.

*Explanation:* When a test statistic falls into the critical region (greater than the critical value $z_\alpha$ in a right-tailed test), it means the result is statistically significant, and we reject the null hypothesis at the given significance level.

---

**(vi) At a toll booth with only one counter, vehicles arrive after a regular interval of 15 minutes on average. It takes 3 minutes for a vehicles to complete the tax payment. What is the traffic intensity at the counter?**

(a) 0.5  
(b) 0.25  
(c) 0.2  
(d) 0.02  

**Answer:** (c) 0.2

*Explanation:*  
Arrival rate ($\lambda$) = 1 vehicle / 15 min.  
Service rate ($\mu$) = 1 vehicle / 3 min.  
Traffic intensity ($\rho$) = $\frac{\lambda}{\mu} = \frac{1/15}{1/3} = \frac{3}{15} = \frac{1}{5} = \mathbf{0.2}$.

---

**(vii) A petrol pump has 4 pumps. The service time follows an exponential distribution with a mean of 5 minutes and vehicles arrive for service in Poisson fashion at a rate of 30 per hour. What is the expected percentage of idle time for each pump?**

(a) 37.5%  
(b) 62.5%  
(c) 52.05%  
(d) 12.25%  

**Answer:** (a) 37.5%

*Explanation:*  
Service rate per pump ($\mu$) = 60 / 5 = 12 vehicles/hr.  
Arrival rate ($\lambda$) = 30 vehicles/hr.  
Number of pumps ($c$) = 4.  

Utilization per pump ($\rho$) = $\frac{\lambda}{c \cdot \mu} = \frac{30}{4 \cdot 12} = \frac{30}{48} = \mathbf{0.625}$ (or 62.5%).  
Hence, the expected idle time for each pump is $1 - \rho = 1 - 0.625 = \mathbf{0.375}$ or **37.5%**.

---
---

## Question 2.

**(a) Show how the Poisson distribution is a limiting case of binomial distribution.**

**Answer:**

The Poisson distribution can be derived as a limiting case of the Binomial distribution under the following conditions:

1. The number of trials $n \rightarrow \infty$ (indefinitely large).
2. The probability of success in a single trial $p \rightarrow 0$ (very small).
3. The mean $np = \lambda$ remains a finite positive constant.

The probability mass function of a Binomial distribution is:

$$P(X=x) = \binom{n}{x} p^x (1-p)^{n-x} = \frac{n(n-1)\dots(n-x+1)}{x!} p^x (1-p)^{n-x}$$

Substitute $p = \frac{\lambda}{n}$:

$$P(X=x) = \frac{n(n-1)\dots(n-x+1)}{x!} \left(\frac{\lambda}{n}\right)^x \left(1-\frac{\lambda}{n}\right)^{n-x}$$

Rearranging the terms:

$$P(X=x) = \frac{\lambda^x}{x!} \left( \frac{n}{n} \cdot \frac{n-1}{n} \dots \frac{n-x+1}{n} \right) \left(1-\frac{\lambda}{n}\right)^n \left(1-\frac{\lambda}{n}\right)^{-x}$$

Taking the limit as $n \rightarrow \infty$:

- $\frac{n-k}{n} = 1 - \frac{k}{n} \rightarrow 1$ for any finite $k$.
- $\left(1-\frac{\lambda}{n}\right)^n \rightarrow e^{-\lambda}$ (standard calculus limit).
- $\left(1-\frac{\lambda}{n}\right)^{-x} \rightarrow 1^x = 1$.

Putting it all together:

$$\lim_{n \rightarrow \infty} P(X=x) = \frac{\lambda^x}{x!} \cdot (1) \cdot e^{-\lambda} \cdot (1) = \frac{\lambda^x e^{-\lambda}}{x!}$$

This is the required probability mass function of the Poisson distribution.

---

**(b) Give the expression for the probability density function of a variable satisfying exponential distribution. Hence, derive expressions for its cumulative distribution function, mean and variance.**

**Answer:**

If $X$ follows an exponential distribution with rate parameter $\lambda > 0$, its Probability Density Function (PDF) is given by:

$$f(x) = \lambda e^{-\lambda x} \quad \text{for } x \ge 0, \text{ and } 0 \text{ otherwise.}$$

**1. Cumulative Distribution Function (CDF):**

$$F(x) = \int_0^x f(t) dt = \int_0^x \lambda e^{-\lambda t} dt$$
$$F(x) = \lambda \left[ \frac{e^{-\lambda t}}{-\lambda} \right]_0^x = -[e^{-\lambda x} - e^0] = \mathbf{1 - e^{-\lambda x}}$$

**2. Mean ($E[X]$):**

$$E[X] = \int_0^\infty x \lambda e^{-\lambda x} dx$$

Applying integration by parts ($u=x$, $dv=\lambda e^{-\lambda x} dx$):

$$E[X] = \left[ -x e^{-\lambda x} \right]_0^\infty - \int_0^\infty 1 \cdot (-e^{-\lambda x}) dx$$
$$E[X] = (0 - 0) + \left[ \frac{-1}{\lambda} e^{-\lambda x} \right]_0^\infty = \mathbf{\frac{1}{\lambda}}$$

**3. Variance ($Var(X)$):**

First, find $E[X^2] = \int_0^\infty x^2 \lambda e^{-\lambda x} dx$.
Similarly applying integration by parts ($u=x^2$, $dv=\lambda e^{-\lambda x} dx$):

$$E[X^2] = \left[ -x^2 e^{-\lambda x} \right]_0^\infty + \int_0^\infty 2x e^{-\lambda x} dx = 0 + \frac{2}{\lambda} \int_0^\infty x \lambda e^{-\lambda x} dx$$
$$E[X^2] = \frac{2}{\lambda} E[X] = \frac{2}{\lambda} \cdot \frac{1}{\lambda} = \frac{2}{\lambda^2}$$

$$\text{Variance} = E[X^2] - (E[X])^2 = \frac{2}{\lambda^2} - \frac{1}{\lambda^2} = \mathbf{\frac{1}{\lambda^2}}$$

---
---

## Question 3.

**(a) Let $X_1, X_2, \dots, X_n$ represent a random sample from the distribution that has pdf $f(x; \theta) = \theta x^{\theta-1}$, $0 < x < 1$, $0 < \theta < \infty$, zero elsewhere. Find the maximum likelihood estimator (mle) of $\theta$.**

**Answer:**

The likelihood function $L(\theta)$ for a random sample of size $n$ is:

$$L(\theta) = \prod_{i=1}^n f(x_i; \theta) = \prod_{i=1}^n \theta x_i^{\theta-1} = \theta^n \left( \prod_{i=1}^n x_i \right)^{\theta-1}$$

Taking the natural logarithm to find the log-likelihood:

$$\ln L(\theta) = n \ln \theta + (\theta - 1) \sum_{i=1}^n \ln x_i$$

To find the MLE, differentiate with respect to $\theta$ and equate to 0:

$$\frac{d}{d\theta} [\ln L(\theta)] = \frac{n}{\theta} + \sum_{i=1}^n \ln x_i = 0$$
$$\frac{n}{\theta} = - \sum_{i=1}^n \ln x_i$$
$$\hat{\theta} = \frac{-n}{\sum_{i=1}^n \ln X_i}$$

Since $0 < X_i < 1$, $\ln X_i$ is negative, ensuring that the estimate $\hat{\theta}$ is positive.  
The MLE of $\theta$ is **$\hat{\theta} = \frac{-n}{\sum_{i=1}^n \ln X_i}$**.

---

**(b) Let $f(x) = 1/2$, $-1 < x < 1$, zero elsewhere be the pdf of a random variable $X$. What is the pdf of $Y = X^2$?**

**Answer:**

The random variable $X$ has a continuous uniform distribution on $(-1, 1)$.
Since $Y = X^2$ and the range of $X$ is $(-1, 1)$, the range of $Y$ is $(0, 1)$.

First, find the CDF of $Y$, $P(Y \le y)$ for $0 < y < 1$:

$$F_Y(y) = P(X^2 \le y) = P(-\sqrt{y} \le X \le \sqrt{y})$$
$$F_Y(y) = \int_{-\sqrt{y}}^{\sqrt{y}} f(x) dx = \int_{-\sqrt{y}}^{\sqrt{y}} \frac{1}{2} dx$$
$$F_Y(y) = \frac{1}{2} [x]_{-\sqrt{y}}^{\sqrt{y}} = \frac{1}{2} (\sqrt{y} - (-\sqrt{y})) = \sqrt{y}$$

The PDF of $Y$ is the derivative of its CDF with respect to $y$:

$$f_Y(y) = \frac{d}{dy} F_Y(y) = \frac{d}{dy} (\sqrt{y}) = \mathbf{\frac{1}{2\sqrt{y}}}$$

So, the pdf of $Y$ is $f_Y(y) = \frac{1}{2\sqrt{y}}$ for $0 < y < 1$, and 0 elsewhere.

---
---

## Question 4.

**(a) Five distinct integers are chosen from the first 10 positive integers. Find the probability that their sum is even.**

**Answer:**

The first 10 positive integers are $\{1, 2, 3, 4, 5, 6, 7, 8, 9, 10\}$.
These contain 5 odd numbers (1, 3, 5, 7, 9) and 5 even numbers (2, 4, 6, 8, 10).

Total ways to pick 5 integers = $\binom{10}{5} = \frac{10 \times 9 \times 8 \times 7 \times 6}{5 \times 4 \times 3 \times 2 \times 1} = 252$.

For the sum of 5 integers to be even, we must pick an **even number of odd integers**. The possible valid combinations of (Odd, Even) are:

- (0 Odd, 5 Even): $\binom{5}{0} \times \binom{5}{5} = 1 \cdot 1 = 1$ way
- (2 Odd, 3 Even): $\binom{5}{2} \times \binom{5}{3} = 10 \cdot 10 = 100$ ways
- (4 Odd, 1 Even): $\binom{5}{4} \times \binom{5}{1} = 5 \cdot 5 = 25$ ways

Total favorable outcomes = $1 + 100 + 25 = 126$.

probability = Favorable / Total = $\frac{126}{252} = \mathbf{\frac{1}{2}}$.

---

**(b) During a study on 100 batteries, the average lifetime was found to be 58 months with a standard deviation of 12 months. However, the company claims that the batteries it produces have an average lifetime of 60 months. Can the hypothesis of 58 months' lifetime be accepted at 5% level of significance? Can it be accepted at 5% level of significance if the company claims that the lifetime is at least 60?**

**Answer:**

Given: Sample size $n = 100$, sample mean $\bar{x} = 58$, standard deviation $s = 12$. Population mean claimed $\mu = 60$.

**Case 1: "The company claims that the average lifetime is 60 months."**

- Null Hypothesis $H_0: \mu = 60$
- Alternative Hypothesis $H_1: \mu \ne 60$ (Two-tailed test)

Since $n \ge 30$, we use the Z-test.
$$Z = \frac{\bar{x} - \mu}{s / \sqrt{n}} = \frac{58 - 60}{12 / \sqrt{100}} = \frac{-2}{1.2} = -1.667$$

At 5% level of significance, the critical values for a two-tailed test are $Z = \pm 1.96$.
**Decision:** Since the calculated $Z (-1.667)$ lies in the acceptance region $[-1.96, 1.96]$, we **fail to reject $H_0$**. Yes, it can be accepted.

**Case 2: "The company claims that the lifetime is at least 60."**

- Null Hypothesis $H_0: \mu \ge 60$
- Alternative Hypothesis $H_1: \mu < 60$ (Left-tailed test)

The test statistic remains $Z = -1.667$.
At 5% level of significance, the critical value for a left-tailed test is $Z = -1.645$.

**Decision:** Since calculated $Z = -1.667 < -1.645$, it falls in the critical/rejection region. Hence we **reject $H_0$**. The claim cannot be accepted.

---
---

## Question 5.

**(a) The manufacturer of wrist watches of a certain company claims that the watches have mean life of 20 years. A random sample of 7 such watches gives the data 18, 21, 26, 15, 17, 15, 21. Can you regard the company's claim to be valid at 1% significance level? (Given that $t_{0.01,6} = 3.707$)**

**Answer:**

Given claim $\mu = 20$. Sample $n=7$, Data = $\{18, 21, 26, 15, 17, 15, 21\}$.

**1. Find sample mean ($\bar{x}$):**
$$\bar{x} = \frac{18 + 21 + 26 + 15 + 17 + 15 + 21}{7} = \frac{133}{7} = 19$$

**2. Find sample standard deviation ($S$):**
$$S^2 = \frac{1}{n-1} \sum (x_i - \bar{x})^2$$

$x_i - \bar{x}$: $-1, 2, 7, -4, -2, -4, 2$
Squares: $1, 4, 49, 16, 4, 16, 4$
Sum of squares = $94$

$$S^2 = \frac{94}{6} = 15.667 \implies S = \sqrt{15.667} \approx 3.958$$

- Null Hypothesis $H_0: \mu = 20$
- Alternative Hypothesis $H_1: \mu \ne 20$ (Two-tailed)

**Test statistic:**
$$t = \frac{\bar{x} - \mu}{S / \sqrt{n}} = \frac{19 - 20}{3.958 / \sqrt{7}} = \frac{-1}{1.496} = -0.668$$

Degrees of freedom $v = n - 1 = 6$. The given critical value is $t = 3.707$.
Since $|-0.668| < 3.707$, the test statistic falls in the acceptance region. We fail to reject the null hypothesis.

**Conclusion:** Yes, the company's claim is valid at the 1% significance level.

---

**(b) Two types of insulin drugs were used on 6 and 5 diabetic patients respectively for reducing their blood sugar levels. Drug A was imported and drug B was indigenous. The decrease percentage in the blood sugar levels are as given. Is there a significant difference in the efficacy of the drugs? Use $t_{0.05} = 2.262$.**
**Drug A:** 9, 10, 12, 10, 14, 13
**Drug B:** 7, 10, 14, 12, 8

**Answer:**

Let $\mu_1, \mu_2$ be the average reductions for Drug A and Drug B respectively.
- $H_0: \mu_1 = \mu_2$ (No significant difference in efficacy)
- $H_1: \mu_1 \ne \mu_2$ (Significant difference)

**For Drug A ($n_1 = 6$):** 
$\bar{x}_1 = \frac{9+10+12+10+14+13}{6} = 11.33$
$\Sigma (x_1 - \bar{x}_1)^2 = (9-11.33)^2 + \dots = 19.333$

**For Drug B ($n_2 = 5$):** 
$\bar{x}_2 = \frac{7+10+14+12+8}{5} = 10.2$
$\Sigma (x_2 - \bar{x}_2)^2 = (7-10.2)^2 + \dots = 32.8$

**Calculate pooled sample variance $S^2$:**
$$S^2 = \frac{\Sigma (x_1 - \bar{x}_1)^2 + \Sigma (x_2 - \bar{x}_2)^2}{n_1 + n_2 - 2} = \frac{19.333 + 32.8}{6 + 5 - 2} = \frac{52.133}{9} \approx 5.793$$
$$S = \sqrt{5.793} \approx 2.407$$

**Calculate the two-sample t-statistic:**
$$t = \frac{\bar{x}_1 - \bar{x}_2}{S \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}} = \frac{11.333 - 10.2}{2.407 \sqrt{\frac{1}{6} + \frac{1}{5}}} = \frac{1.133}{2.407 \sqrt{0.3667}} = \frac{1.133}{2.407 \times 0.605} = \frac{1.133}{1.457} \approx 0.778$$

Degrees of freedom $v = n_1 + n_2 - 2 = 9$.
Given critical value $t_{0.05, 9} = 2.262$.
Since calculated $t = 0.778 < 2.262$, we fail to reject the null hypothesis.

**Conclusion:** There is no significant difference in the efficacy of the two drugs.
