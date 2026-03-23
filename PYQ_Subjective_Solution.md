# B.Tech. 3rd Semester Examination (NEP)
**Subject:** Probability and Statistics (BSC-302)  
**Paper Code:** 302  
**Subjective Questions — Detailed Solutions**

---
---

## Question 2.

**(a) Show how the Poisson distribution is a limiting case of binomial distribution.**

**Answer:**

The Poisson distribution can be derived as a limiting case of the Binomial distribution under the following conditions:

1. The number of trials $n \rightarrow \infty$ (indefinitely large).
2. The probability of success in a single trial $p \rightarrow 0$ (very small).
3. The mean $np = \lambda$ remains a finite positive constant.

**Proof:**

The probability mass function of a Binomial distribution is:

$$P(X=x) = \binom{n}{x} p^x (1-p)^{n-x}$$

Expanding:

$$P(X=x) = \frac{n!}{x!(n-x)!} p^x (1-p)^{n-x}$$

$$= \frac{n(n-1)(n-2)\dots(n-x+1)}{x!} p^x (1-p)^{n-x}$$

Substitute $p = \frac{\lambda}{n}$ (since $np = \lambda$):

$$P(X=x) = \frac{n(n-1)(n-2)\dots(n-x+1)}{x!} \left(\frac{\lambda}{n}\right)^x \left(1-\frac{\lambda}{n}\right)^{n-x}$$

Rearranging the terms:

$$P(X=x) = \frac{\lambda^x}{x!} \cdot \underbrace{\frac{n}{n} \cdot \frac{n-1}{n} \cdot \frac{n-2}{n} \dots \frac{n-x+1}{n}}_{\text{x terms}} \cdot \left(1-\frac{\lambda}{n}\right)^n \cdot \left(1-\frac{\lambda}{n}\right)^{-x}$$

Taking the limit as $n \rightarrow \infty$:

- Each factor $\frac{n-k}{n} = 1 - \frac{k}{n} \rightarrow 1$ for any finite $k$.
- $\left(1-\frac{\lambda}{n}\right)^n \rightarrow e^{-\lambda}$ (standard calculus limit).
- $\left(1-\frac{\lambda}{n}\right)^{-x} \rightarrow 1^{-x} = 1$ (since $x$ is finite).

Putting it all together:

$$\boxed{\lim_{n \rightarrow \infty} P(X=x) = \frac{\lambda^x e^{-\lambda}}{x!}, \quad x = 0, 1, 2, \dots}$$

This is the probability mass function of the **Poisson distribution** with parameter $\lambda$. Hence proved.

---

**(b) Give the expression for the probability density function of a variable satisfying exponential distribution. Hence, derive expressions for its cumulative distribution function, mean and variance.**

**Answer:**

If $X$ follows an exponential distribution with rate parameter $\lambda > 0$, its **Probability Density Function (PDF)** is:

$$f(x) = \begin{cases} \lambda e^{-\lambda x}, & x \ge 0 \\ 0, & \text{otherwise} \end{cases}$$

### 1. Cumulative Distribution Function (CDF):

$$F(x) = P(X \le x) = \int_0^x \lambda e^{-\lambda t} \, dt$$

$$= \lambda \left[ \frac{e^{-\lambda t}}{-\lambda} \right]_0^x = -\left[e^{-\lambda x} - e^0\right]$$

$$\boxed{F(x) = 1 - e^{-\lambda x}, \quad x \ge 0}$$

### 2. Mean ($E[X]$):

$$E[X] = \int_0^\infty x \cdot \lambda e^{-\lambda x} \, dx$$

Using integration by parts with $u = x$, $dv = \lambda e^{-\lambda x} dx$:

$$= \left[-x e^{-\lambda x}\right]_0^\infty + \int_0^\infty e^{-\lambda x} \, dx$$

$$= 0 + \left[\frac{-1}{\lambda} e^{-\lambda x}\right]_0^\infty = 0 - \left(\frac{-1}{\lambda}\right)$$

$$\boxed{E[X] = \frac{1}{\lambda}}$$

### 3. Variance ($\text{Var}(X)$):

First, find $E[X^2]$:

$$E[X^2] = \int_0^\infty x^2 \cdot \lambda e^{-\lambda x} \, dx$$

Using integration by parts with $u = x^2$, $dv = \lambda e^{-\lambda x} dx$:

$$= \left[-x^2 e^{-\lambda x}\right]_0^\infty + \int_0^\infty 2x e^{-\lambda x} \, dx$$

$$= 0 + \frac{2}{\lambda} \int_0^\infty x \cdot \lambda e^{-\lambda x} \, dx = \frac{2}{\lambda} \cdot E[X] = \frac{2}{\lambda} \cdot \frac{1}{\lambda} = \frac{2}{\lambda^2}$$

$$\text{Var}(X) = E[X^2] - (E[X])^2 = \frac{2}{\lambda^2} - \frac{1}{\lambda^2}$$

$$\boxed{\text{Var}(X) = \frac{1}{\lambda^2}}$$

---
---

## Question 3.

**(a) Let $X_1, X_2, \dots, X_n$ represent a random sample from the distribution that has pdf $f(x; \theta) = \theta x^{\theta-1}$, $0 < x < 1$, $0 < \theta < \infty$, zero elsewhere. Find the maximum likelihood estimator (MLE) of $\theta$.**

**Answer:**

**Step 1: Write the Likelihood Function**

$$L(\theta) = \prod_{i=1}^n f(x_i; \theta) = \prod_{i=1}^n \theta x_i^{\theta-1} = \theta^n \left(\prod_{i=1}^n x_i\right)^{\theta-1}$$

**Step 2: Take the Log-Likelihood**

$$\ln L(\theta) = n \ln \theta + (\theta - 1) \sum_{i=1}^n \ln x_i$$

**Step 3: Differentiate and set equal to zero**

$$\frac{d}{d\theta} [\ln L(\theta)] = \frac{n}{\theta} + \sum_{i=1}^n \ln x_i = 0$$

**Step 4: Solve for $\theta$**

$$\frac{n}{\theta} = -\sum_{i=1}^n \ln x_i$$

$$\boxed{\hat{\theta}_{MLE} = \frac{-n}{\sum_{i=1}^n \ln X_i}}$$

**Note:** Since $0 < X_i < 1$, each $\ln X_i < 0$, so $\sum \ln X_i < 0$, making $\hat{\theta} > 0$ ✓

**Verification (Second derivative test):**

$$\frac{d^2}{d\theta^2} [\ln L] = -\frac{n}{\theta^2} < 0$$

This confirms that the solution is indeed a maximum.

---

**(b) Let $f(x) = \frac{1}{2}$, $-1 < x < 1$, zero elsewhere be the pdf of a random variable $X$. What is the pdf of $Y = X^2$?**

**Answer:**

$X$ is uniformly distributed on $(-1, 1)$. Since $Y = X^2$ and $-1 < X < 1$, the range of $Y$ is $(0, 1)$.

**Step 1: Find the CDF of $Y$**

For $0 < y < 1$:

$$F_Y(y) = P(Y \le y) = P(X^2 \le y) = P(-\sqrt{y} \le X \le \sqrt{y})$$

$$= \int_{-\sqrt{y}}^{\sqrt{y}} \frac{1}{2} \, dx = \frac{1}{2} \left[x\right]_{-\sqrt{y}}^{\sqrt{y}} = \frac{1}{2}\left(\sqrt{y} - (-\sqrt{y})\right) = \sqrt{y}$$

**Step 2: Differentiate to find the PDF**

$$f_Y(y) = \frac{d}{dy} F_Y(y) = \frac{d}{dy} \sqrt{y} = \frac{1}{2} y^{-1/2}$$

$$\boxed{f_Y(y) = \frac{1}{2\sqrt{y}}, \quad 0 < y < 1, \quad \text{zero elsewhere.}}$$

---
---

## Question 4.

**(a) Five distinct integers are chosen from the first 10 positive integers. Find the probability that their sum is even.**

**Answer:**

The first 10 positive integers are $\{1, 2, 3, 4, 5, 6, 7, 8, 9, 10\}$.
- **Odd numbers:** $\{1, 3, 5, 7, 9\}$ — 5 numbers
- **Even numbers:** $\{2, 4, 6, 8, 10\}$ — 5 numbers

**Total ways** to choose 5 from 10:

$$\binom{10}{5} = 252$$

**Condition for even sum:** The number of odd integers chosen must be **even** (0, 2, or 4).

| Odd chosen | Even chosen | No. of ways |
|:---:|:---:|:---:|
| 0 | 5 | $\binom{5}{0} \times \binom{5}{5} = 1 \times 1 = 1$ |
| 2 | 3 | $\binom{5}{2} \times \binom{5}{3} = 10 \times 10 = 100$ |
| 4 | 1 | $\binom{5}{4} \times \binom{5}{1} = 5 \times 5 = 25$ |

**Total favorable** = $1 + 100 + 25 = 126$

$$\boxed{P(\text{sum is even}) = \frac{126}{252} = \frac{1}{2}}$$

---

**(b) During a study on 100 batteries, the average lifetime was found to be 58 months with a standard deviation of 12 months. However, the company claims that the batteries it produces have an average lifetime of 60 months. Can the hypothesis of 58 months' lifetime be accepted at 5% level of significance? Can it be accepted at 5% level of significance if the company claims that the lifetime is at least 60?**

**Answer:**

**Given:** $n = 100$, $\bar{x} = 58$, $s = 12$, claimed $\mu_0 = 60$.

Since $n = 100 \ge 30$, we use the **Z-test** (large sample test).

**Test statistic:**

$$Z = \frac{\bar{x} - \mu_0}{s / \sqrt{n}} = \frac{58 - 60}{12 / \sqrt{100}} = \frac{-2}{1.2} = -1.667$$

### Case 1: Two-tailed test (Claim: $\mu = 60$)

- $H_0: \mu = 60$
- $H_1: \mu \ne 60$

At 5% significance, critical values = $\pm Z_{0.025} = \pm 1.96$.

Since $|Z| = 1.667 < 1.96$, the test statistic lies in the **acceptance region**.

**Decision:** We **fail to reject $H_0$**. The hypothesis that $\mu = 60$ **can be accepted** at 5% level.

### Case 2: Left-tailed test (Claim: $\mu \ge 60$)

- $H_0: \mu \ge 60$
- $H_1: \mu < 60$

At 5% significance, critical value = $-Z_{0.05} = -1.645$.

Since $Z = -1.667 < -1.645$, the test statistic falls in the **rejection region**.

**Decision:** We **reject $H_0$**. The claim that the lifetime is at least 60 months **cannot be accepted** at 5% level.

---
---

## Question 5.

**(a) The manufacturer of wrist watches of a certain company claims that the watches have mean life of 20 years. A random sample of 7 such watches gives the data 18, 21, 26, 15, 17, 15, 21. Can you regard the company's claim to be valid at 1% significance level? (Given that $t_{0.01,6} = 3.707$)**

**Answer:**

**Given:** Claimed $\mu_0 = 20$, $n = 7$, Data: $18, 21, 26, 15, 17, 15, 21$.

Since $n < 30$, we use the **t-test**.

**Step 1: Sample Mean**

$$\bar{x} = \frac{18 + 21 + 26 + 15 + 17 + 15 + 21}{7} = \frac{133}{7} = 19$$

**Step 2: Sample Standard Deviation**

| $x_i$ | $x_i - \bar{x}$ | $(x_i - \bar{x})^2$ |
|:---:|:---:|:---:|
| 18 | −1 | 1 |
| 21 | 2 | 4 |
| 26 | 7 | 49 |
| 15 | −4 | 16 |
| 17 | −2 | 4 |
| 15 | −4 | 16 |
| 21 | 2 | 4 |

$$\sum (x_i - \bar{x})^2 = 1 + 4 + 49 + 16 + 4 + 16 + 4 = 94$$

$$S = \sqrt{\frac{\sum(x_i - \bar{x})^2}{n-1}} = \sqrt{\frac{94}{6}} = \sqrt{15.667} \approx 3.958$$

**Step 3: Hypothesis**

- $H_0: \mu = 20$ (Claim is valid)
- $H_1: \mu \ne 20$ (Two-tailed test)

**Step 4: Test Statistic**

$$t = \frac{\bar{x} - \mu_0}{S / \sqrt{n}} = \frac{19 - 20}{3.958 / \sqrt{7}} = \frac{-1}{3.958 / 2.646} = \frac{-1}{1.496} = -0.668$$

**Step 5: Decision**

Degrees of freedom $\nu = n - 1 = 6$.

Critical value: $t_{0.01, 6} = 3.707$ (two-tailed, so rejection region is $|t| > 3.707$).

Since $|t| = 0.668 < 3.707$, the test statistic lies in the **acceptance region**.

$$\boxed{\text{The company's claim is valid at the 1\% significance level.}}$$

---

**(b) Two types of insulin drugs were used on 6 and 5 diabetic patients respectively for reducing their blood sugar levels. Drug A was imported and drug B was indigenous. The decrease percentage in the blood sugar levels are as given. Is there a significant difference in the efficacy of the drugs? Use $t_{0.05} = 2.262$.**

**Drug A:** 9, 10, 12, 10, 14, 13  
**Drug B:** 7, 10, 14, 12, 8

**Answer:**

This is a **two-sample t-test** (independent samples, equal variances assumed).

- $H_0: \mu_1 = \mu_2$ (No significant difference)
- $H_1: \mu_1 \ne \mu_2$ (Significant difference — two-tailed)

**For Drug A ($n_1 = 6$):**

$$\bar{x}_1 = \frac{9 + 10 + 12 + 10 + 14 + 13}{6} = \frac{68}{6} = 11.333$$

| $x_i$ | $x_i - 11.333$ | $(x_i - 11.333)^2$ |
|:---:|:---:|:---:|
| 9 | −2.333 | 5.444 |
| 10 | −1.333 | 1.778 |
| 12 | 0.667 | 0.444 |
| 10 | −1.333 | 1.778 |
| 14 | 2.667 | 7.111 |
| 13 | 1.667 | 2.778 |

$$\sum(x_i - \bar{x}_1)^2 = 5.444 + 1.778 + 0.444 + 1.778 + 7.111 + 2.778 = 19.333$$

**For Drug B ($n_2 = 5$):**

$$\bar{x}_2 = \frac{7 + 10 + 14 + 12 + 8}{5} = \frac{51}{5} = 10.2$$

| $x_i$ | $x_i - 10.2$ | $(x_i - 10.2)^2$ |
|:---:|:---:|:---:|
| 7 | −3.2 | 10.24 |
| 10 | −0.2 | 0.04 |
| 14 | 3.8 | 14.44 |
| 12 | 1.8 | 3.24 |
| 8 | −2.2 | 4.84 |

$$\sum(x_i - \bar{x}_2)^2 = 10.24 + 0.04 + 14.44 + 3.24 + 4.84 = 32.80$$

**Pooled Variance:**

$$S_p^2 = \frac{\sum(x_i - \bar{x}_1)^2 + \sum(x_i - \bar{x}_2)^2}{n_1 + n_2 - 2} = \frac{19.333 + 32.80}{6 + 5 - 2} = \frac{52.133}{9} = 5.793$$

$$S_p = \sqrt{5.793} \approx 2.407$$

**Test Statistic:**

$$t = \frac{\bar{x}_1 - \bar{x}_2}{S_p \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}} = \frac{11.333 - 10.2}{2.407\sqrt{\frac{1}{6} + \frac{1}{5}}} = \frac{1.133}{2.407 \times \sqrt{0.3667}}$$

$$= \frac{1.133}{2.407 \times 0.6056} = \frac{1.133}{1.458} \approx 0.777$$

**Decision:**

Degrees of freedom $\nu = n_1 + n_2 - 2 = 9$.

Critical value: $t_{0.05, 9} = 2.262$ (two-tailed).

Since $|t| = 0.777 < 2.262$, the test statistic lies in the **acceptance region**.

$$\boxed{\text{There is no significant difference in the efficacy of the two drugs.}}$$

---
---

## Question 6.

**(a) At a passport office, applicants arrive for document verification according to Poisson distribution at a rate of 24 per hour, but the waiting room cannot accommodate more than 4 people at a time. The time it takes for one applicant to get his documents verified is 5 minutes per patient. Find the probability that an applicant who arrives will not have to wait. Hence, find the effective rate and the average waiting time for a new applicant who arrives at the passport office.**

**Answer:**

This is an **M/M/1/K** (finite capacity) queuing problem with $K = 4$ (system capacity = 4, including the one being served).

**Given:**
- Arrival rate: $\lambda = 24$ per hour = $\frac{24}{60} = 0.4$ per minute
- Service time: 5 minutes per applicant → Service rate: $\mu = \frac{1}{5} = 0.2$ per minute
- System capacity: $K = 4$ (waiting room holds 4, but since 1 is being served, total in system ≤ 4+1 = 5)

**Wait — let me re-read:** "the waiting room cannot accommodate more than 4 people at a time" and the service takes 5 min. So total system capacity = 4 (waiting) + 1 (in service) = **5**.

Let $K = 5$ (maximum number in system).

**Traffic intensity:**

$$\rho = \frac{\lambda}{\mu} = \frac{0.4}{0.2} = 2$$

Since $\rho \ne 1$, for an M/M/1/K queue:

$$P_0 = \frac{1 - \rho}{1 - \rho^{K+1}} = \frac{1 - 2}{1 - 2^{6}} = \frac{-1}{1 - 64} = \frac{-1}{-63} = \frac{1}{63}$$

$$P_n = P_0 \cdot \rho^n = \frac{\rho^n}{63}$$

**Probability that an arriving applicant will NOT have to wait:**

The applicant doesn't wait if the system has 0 people (server idle):

$$P_0 = \frac{1}{63} \approx 0.0159$$

**Effective arrival rate:**

An arriving customer is lost if system is full (has K people). So:

$$\lambda_{\text{eff}} = \lambda (1 - P_K) = \lambda \left(1 - P_5\right) = 0.4 \left(1 - \frac{2^5}{63}\right) = 0.4 \left(1 - \frac{32}{63}\right) = 0.4 \times \frac{31}{63}$$

$$\lambda_{\text{eff}} = \frac{12.4}{63} \approx 0.1968 \text{ per minute} \approx 11.81 \text{ per hour}$$

**Average number in the system ($L_s$):**

$$L_s = \frac{\rho}{1 - \rho}\left[\frac{1 - (K+1)\rho^K + K\rho^{K+1}}{1 - \rho^{K+1}}\right]$$

$$= \frac{2}{1 - 2}\left[\frac{1 - 6 \cdot 2^5 + 5 \cdot 2^6}{1 - 2^6}\right]$$

$$= \frac{2}{-1}\left[\frac{1 - 192 + 320}{1 - 64}\right] = -2 \times \frac{129}{-63} = \frac{258}{63} \approx 4.095$$

**Average waiting time in the system ($W_s$):**

Using Little's formula: $L_s = \lambda_{\text{eff}} \cdot W_s$

$$W_s = \frac{L_s}{\lambda_{\text{eff}}} = \frac{4.095}{0.1968} \approx 20.81 \text{ minutes}$$

**Average waiting time in the queue ($W_q$):**

$$W_q = W_s - \frac{1}{\mu} = 20.81 - 5 = 15.81 \text{ minutes}$$

$$\boxed{P(\text{no wait}) = \frac{1}{63} \approx 0.016, \quad \lambda_{\text{eff}} \approx 11.81/\text{hr}, \quad W_q \approx 15.81 \text{ min}}$$

---

**(b) At an office, there are two computers for carrying out a particular job. The average time per job on each computer is 15 minutes and the average rate is 3 jobs for an hour. Assume that the job times are distributed exponentially. If the maximum number of jobs accepted on a day is 3, find the expected number of jobs that wait for the computer and the total time lost per day.**

**Answer:**

This is an **M/M/2/3** queuing model (2 servers, max 3 in system).

**Given:**
- Number of servers: $c = 2$
- Arrival rate: $\lambda = 3$ jobs/hr
- Service rate per server: $\mu = \frac{60}{15} = 4$ jobs/hr
- Maximum system capacity: $K = 3$

**Traffic intensity per server:**

$$\rho = \frac{\lambda}{c\mu} = \frac{3}{2 \times 4} = \frac{3}{8} = 0.375$$

For an M/M/c/K queue, the state probabilities are:

$$P_n = \begin{cases} \frac{(\lambda/\mu)^n}{n!} P_0, & 0 \le n \le c \\ \frac{(\lambda/\mu)^n}{c! \cdot c^{n-c}} P_0, & c \le n \le K \end{cases}$$

Let $a = \lambda/\mu = 3/4 = 0.75$.

**State probabilities:**

- $P_0 = P_0$
- $P_1 = \frac{a^1}{1!} P_0 = 0.75 P_0$
- $P_2 = \frac{a^2}{2!} P_0 = \frac{0.5625}{2} P_0 = 0.28125 P_0$
- $P_3 = \frac{a^3}{c! \cdot c^{3-2}} P_0 = \frac{0.4219}{2 \times 2} P_0 = 0.10547 P_0$

**Normalization:** $P_0 + P_1 + P_2 + P_3 = 1$

$$P_0 (1 + 0.75 + 0.28125 + 0.10547) = 1$$

$$P_0 \times 2.13672 = 1 \implies P_0 = 0.4680$$

So:
- $P_0 = 0.4680$
- $P_1 = 0.3510$
- $P_2 = 0.1316$
- $P_3 = 0.0494$

**Expected number of jobs waiting in queue ($L_q$):**

Jobs wait only when $n > c = 2$ (both servers busy):

$$L_q = \sum_{n=c+1}^{K} (n - c) P_n = (3 - 2) P_3 = 1 \times P_3 = 0.0494$$

$$\boxed{L_q \approx 0.0494 \text{ jobs}}$$

**Effective arrival rate:**

$$\lambda_{\text{eff}} = \lambda(1 - P_K) = 3(1 - 0.0494) = 3 \times 0.9506 = 2.852 \text{ jobs/hr}$$

**Average waiting time in queue:**

$$W_q = \frac{L_q}{\lambda_{\text{eff}}} = \frac{0.0494}{2.852} \approx 0.01732 \text{ hr} \approx 1.04 \text{ minutes}$$

**Total time lost per day (8 hr working day):**

Total jobs per day $= \lambda_{\text{eff}} \times 8 = 2.852 \times 8 = 22.82$ jobs

Total waiting time lost per day $= W_q \times \lambda_{\text{eff}} \times 8 = L_q \times 8 = 0.0494 \times 8 \approx 0.395$ hours $\approx 23.7$ minutes

$$\boxed{\text{Expected jobs waiting} \approx 0.05, \quad \text{Total time lost/day} \approx 23.7 \text{ min}}$$

---
---

## Question 7. Answer any four of the following: (3.5 × 4 = 14)

**(a) State and prove the multiplication rules of probability.**

**Answer:**

**Statement:** For any two events $A$ and $B$:

$$P(A \cap B) = P(A) \cdot P(B|A) = P(B) \cdot P(A|B)$$

where $P(B|A)$ is the conditional probability of $B$ given $A$ has occurred.

**If $A$ and $B$ are independent**, then $P(B|A) = P(B)$, so:

$$P(A \cap B) = P(A) \cdot P(B)$$

**Proof:**

By the definition of conditional probability:

$$P(B|A) = \frac{P(A \cap B)}{P(A)}, \quad \text{provided } P(A) > 0$$

Rearranging:

$$P(A \cap B) = P(A) \cdot P(B|A)$$

Similarly:

$$P(A|B) = \frac{P(A \cap B)}{P(B)}, \quad \text{provided } P(B) > 0$$

Rearranging:

$$P(A \cap B) = P(B) \cdot P(A|B)$$

**Extension to three events:**

$$P(A \cap B \cap C) = P(A) \cdot P(B|A) \cdot P(C|A \cap B)$$

**Proof:** Apply the rule twice:

$$P(A \cap B \cap C) = P((A \cap B) \cap C) = P(A \cap B) \cdot P(C | A \cap B)$$

$$= P(A) \cdot P(B|A) \cdot P(C | A \cap B) \quad \blacksquare$$

---

**(b) State and prove Chebyshev's inequality.**

**Answer:**

**Statement:** For any random variable $X$ with mean $\mu$ and finite variance $\sigma^2$, for any $k > 0$:

$$P(|X - \mu| \ge k\sigma) \le \frac{1}{k^2}$$

Equivalently: $P(|X - \mu| < k\sigma) \ge 1 - \frac{1}{k^2}$

**Proof (for continuous case):**

$$\sigma^2 = E[(X - \mu)^2] = \int_{-\infty}^{\infty} (x - \mu)^2 f(x) \, dx$$

$$\ge \int_{|x - \mu| \ge k\sigma} (x - \mu)^2 f(x) \, dx$$

(We dropped the non-negative integrand over the region $|x - \mu| < k\sigma$)

In the region $|x - \mu| \ge k\sigma$, we have $(x - \mu)^2 \ge k^2 \sigma^2$. Therefore:

$$\sigma^2 \ge k^2 \sigma^2 \int_{|x - \mu| \ge k\sigma} f(x) \, dx = k^2 \sigma^2 \cdot P(|X - \mu| \ge k\sigma)$$

Dividing both sides by $k^2 \sigma^2$:

$$P(|X - \mu| \ge k\sigma) \le \frac{\sigma^2}{k^2 \sigma^2} = \frac{1}{k^2} \quad \blacksquare$$

---

**(c) State the differences between a parameter and a statistic.**

**Answer:**

| Feature | Parameter | Statistic |
|:---|:---|:---|
| **Definition** | A numerical characteristic of a **population** | A numerical characteristic of a **sample** |
| **Nature** | It is a **fixed constant** (usually unknown) | It is a **random variable** (varies from sample to sample) |
| **Notation** | Greek letters ($\mu$, $\sigma$, $p$, $\theta$) | Roman letters ($\bar{x}$, $s$, $\hat{p}$, $\hat{\theta}$) |
| **Computation** | Computed from the **entire population** | Computed from a **sample** drawn from the population |
| **Variability** | No variability — it is a constant | Has variability — it has a sampling distribution |
| **Purpose** | Describes the population | Used to **estimate** the population parameter |
| **Example** | Population mean $\mu = \frac{\sum X_i}{N}$ | Sample mean $\bar{x} = \frac{\sum x_i}{n}$ |
| **Knowability** | Typically **unknown** in practice | **Known** — computed from observed data |

---

**(d) A random sample of 100 items gives the mean 5.4 and variance 10.25. Can it be regarded as drawn from a normal population with mean 6 at 5% level of significance?**

**Answer:**

**Given:** $n = 100$, $\bar{x} = 5.4$, $s^2 = 10.25$ (so $s = \sqrt{10.25} \approx 3.202$), $\mu_0 = 6$, $\alpha = 0.05$.

**Hypotheses:**
- $H_0: \mu = 6$
- $H_1: \mu \ne 6$ (Two-tailed test)

Since $n = 100 \ge 30$, we use the **Z-test**.

**Test Statistic:**

$$Z = \frac{\bar{x} - \mu_0}{s / \sqrt{n}} = \frac{5.4 - 6}{\sqrt{10.25} / \sqrt{100}} = \frac{-0.6}{3.202 / 10} = \frac{-0.6}{0.3202} = -1.874$$

**Critical value** at 5% significance (two-tailed): $Z_{\alpha/2} = Z_{0.025} = 1.96$.

**Decision:** Since $|Z| = 1.874 < 1.96$, the test statistic lies in the **acceptance region**.

$$\boxed{\text{Yes, the sample can be regarded as drawn from a normal population with mean 6.}}$$

---

**(e) Explain the type of errors in hypothesis testing.**

**Answer:**

In hypothesis testing, two types of errors can occur:

### Type I Error (α error — False Positive)

- **Definition:** Rejecting the null hypothesis $H_0$ when it is actually **true**.
- **Probability:** $\alpha$ = Level of significance
- **Example:** Concluding that a drug is effective when it actually is not.
- $\alpha = P(\text{Reject } H_0 | H_0 \text{ is true})$

### Type II Error (β error — False Negative)

- **Definition:** Failing to reject (accepting) the null hypothesis $H_0$ when it is actually **false**.
- **Probability:** $\beta$
- **Example:** Concluding that a drug is not effective when it actually is effective.
- $\beta = P(\text{Fail to reject } H_0 | H_0 \text{ is false})$

### Summary Table

| | $H_0$ is True | $H_0$ is False |
|:---|:---:|:---:|
| **Reject $H_0$** | Type I Error ($\alpha$) | Correct Decision (Power = $1 - \beta$) |
| **Fail to Reject $H_0$** | Correct Decision | Type II Error ($\beta$) |

### Key Relationships

1. **Power of the test** $= 1 - \beta$ = Probability of correctly rejecting a false $H_0$.
2. $\alpha$ and $\beta$ are **inversely related**: Decreasing $\alpha$ increases $\beta$, and vice versa (for a fixed sample size).
3. Increasing **sample size** $n$ reduces both $\alpha$ and $\beta$ simultaneously.
4. Type I error is generally considered more serious, which is why we fix $\alpha$ (e.g., 0.05 or 0.01) before conducting the test.
