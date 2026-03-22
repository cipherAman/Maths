# 3. Special Distributions

This section covers common conceptual probability distributions.

---

## Part A: Discrete Distributions

### 3.1 Binomial Distribution

The binomial distribution models the number of successes in a fixed number of independent 'yes/no' (Bernoulli) trials, where each trial yields success with the same probability $p$.

**Parameters:**
- $n$: Number of trials.
- $p$: Probability of success on a single trial.
- $q = 1 - p$: Probability of failure on a single trial.

**Random Variable:** $X = $ number of successes in $n$ trials. $X \in \{0, 1, 2, \dots, n\}$.

**Probability Mass Function (PMF):**
$$ P(X = x) = \binom{n}{x} p^x q^{n-x} $$
where $\binom{n}{x} = \frac{n!}{x!(n-x)!}$

**Mean and Variance:**
- Mean: $\mu = E[X] = np$
- Variance: $\sigma^2 = Var(X) = npq$

**Example Applications:**
- Tossing a coin 10 times and counting the number of heads.
- Number of defective items in a batch of $n$ items, if each item has probability $p$ of being defective independent of others.

---

### 3.2 Hypergeometric Distribution

The hypergeometric distribution is used when samples are drawn from a finite population *without replacement*. Unlike the binomial distribution, the probability of success changes with each draw.

**Parameters:**
- $N$: Total population size.
- $K$: Total number of success states in the population.
- $n$: Number of draws (sample size).

**Random Variable:** $X = $ number of successes in $n$ draws without replacement.

**Probability Mass Function (PMF):**
$$ P(X = x) = \frac{\binom{K}{x} \binom{N-K}{n-x}}{\binom{N}{n}} $$

**Conditions:**
$\max(0, n - (N - K)) \le x \le \min(n, K)$

**Mean and Variance:**
- Mean: $\mu = E[X] = n \cdot \frac{K}{N}$
- Variance: $\sigma^2 = n \cdot \frac{K}{N} \cdot \left(1 - \frac{K}{N}\right) \cdot \frac{N-n}{N-1}$
*(Note that $\frac{N-n}{N-1}$ is the "finite population correction factor".)*

**Difference from Binomial:**
If the population size $N$ is very large compared to the sample size $n$, the draws are nearly independent, and the hypergeometric distribution can be approximated by the binomial distribution with $p = K/N$.

---

### 3.3 Poisson Distribution

The Poisson distribution expresses the probability of a given number of events occurring in a fixed interval of time or space, assuming these events occur with a known constant mean rate and independently of the time since the last event.

**Parameter:**
- $\lambda$ (lambda): The average number of events in an interval.

**Random Variable:** $X = $ number of occurrences of the event in the fixed interval. $X \in \{0, 1, 2, 3, \dots\}$.

**Probability Mass Function (PMF):**
$$ P(X = x) = \frac{e^{-\lambda} \lambda^x}{x!} $$
where $e \approx 2.71828$.

**Mean and Variance:**
- Mean: $\mu = E[X] = \lambda$
- Variance: $\sigma^2 = Var(X) = \lambda$
*(A unique characteristic of the Poisson distribution is that its mean and variance are equal).*

**Poisson Approximation to Binomial:**
If $n$ is very large ($n \to \infty$) and $p$ is very small ($p \to 0$) such that $np = \lambda$ (a constant), the binomial distribution approaches the Poisson distribution.

---

## Part B: Continuous Distributions

### 3.4 Uniform Distribution (Continuous)

A continuous uniform distribution (or rectangular distribution) characterizes a random variable that is equally likely to take any value within a specified interval $[a, b]$.

**Parameters:**
- $a$: Minimum constraint (lower bound).
- $b$: Maximum constraint (upper bound).

**Probability Density Function (PDF):**
$$ f(x) = \begin{cases} \frac{1}{b - a} & \text{for } a \le x \le b \\ 0 & \text{otherwise} \end{cases} $$

**Cumulative Distribution Function (CDF):**
$$ F(x) = \begin{cases} 0 & \text{for } x < a \\ \frac{x - a}{b - a} & \text{for } a \le x \le b \\ 1 & \text{for } x > b \end{cases} $$

**Mean and Variance:**
- Mean: $\mu = \frac{a + b}{2}$
- Variance: $\sigma^2 = \frac{(b - a)^2}{12}$

---

### 3.5 Exponential Distribution

The exponential distribution models the time elapsed between events in a Poisson point process (a process in which events occur continuously and independently at a constant average rate).

**Parameter:**
- $\lambda > 0$: The rate parameter (often the number of events per unit time). This is the same $\lambda$ used in the Poisson process.

**Probability Density Function (PDF):**
$$ f(x) = \begin{cases} \lambda e^{-\lambda x} & \text{for } x \ge 0 \\ 0 & \text{for } x < 0 \end{cases} $$

**Cumulative Distribution Function (CDF):**
$$ F(x) = \begin{cases} 1 - e^{-\lambda x} & \text{for } x \ge 0 \\ 0 & \text{for } x < 0 \end{cases} $$

**Mean and Variance:**
- Mean: $\mu = E[X] = \frac{1}{\lambda}$ ($E[X]$ is often denoted as $\theta = 1/\lambda$, the expected time between events).
- Variance: $\sigma^2 = Var(X) = \frac{1}{\lambda^2}$

**Memoryless Property:**
A defining characteristic of the exponential distribution is its "memoryless" property:
$P(X > s + t \mid X > s) = P(X > t)$
This means the probability of waiting an additional time $t$ doesn't depend on how long you have already waited ($s$).

---

### 3.6 Normal Distribution

The Normal (or Gaussian) distribution is the most important probability distribution in statistics due to the Central Limit Theorem. It forms a symmetric bell-shaped curve.

**Parameters:**
- $\mu$: Mean (central location of the distribution).
- $\sigma^2$: Variance (spread of the distribution). $\sigma$ is the standard deviation.
Notation: $X \sim N(\mu, \sigma^2)$

**Probability Density Function (PDF):**
$$ f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x - \mu}{\sigma}\right)^2} $$
for $-\infty < x < \infty$.

**Features of the Normal Curve:**
1. Symmetric about the center, $\mu$.
2. The mean, median, and mode are all equal.
3. Total area under the curve is $1$.
4. **Empirical Rule (68-95-99.7% Rule):**
   - Approx. 68% of data falls within $1\sigma$ of the mean ($\mu \pm \sigma$).
   - Approx. 95% of data falls within $2\sigma$ of the mean ($\mu \pm 2\sigma$).
   - Approx. 99.7% of data falls within $3\sigma$ of the mean ($\mu \pm 3\sigma$).

**Standard Normal Distribution:**
If we standardize a normal variable $X$ by defining $Z = \frac{X - \mu}{\sigma}$, then $Z$ has a Standard Normal Distribution with mean $0$ and variance $1$: $Z \sim N(0, 1)$.
The PDF of $Z$ is:
$$ \phi(z) = \frac{1}{\sqrt{2\pi}} e^{-z^2/2} $$
This allows us to use standard normal tables to find probabilities.
