# 2. Mean, Variance, and Inequalities

## 2.1 Mean (Expected Value)

The **Mean**, also known as the **Expected Value** or **Expectation**, is a measure of the central tendency of a random variable. It represents the long-run average value of repetitions of the experiment it represents. It is denoted by $\mu$ or $E[X]$.

### For Discrete Random Variables:
If $X$ is a discrete random variable with PMF $p(x)$, the expected value is:
$$ E[X] = \mu = \sum_{x} x \cdot p(x) $$

### For Continuous Random Variables:
If $X$ is a continuous random variable with PDF $f(x)$, the expected value is:
$$ E[X] = \mu = \int_{-\infty}^{\infty} x \cdot f(x) dx $$

**Properties of Expectation:**
If $a$ and $b$ are constants:
1. $E[c] = c$ (Expectation of a constant is the constant itself)
2. $E[aX + b] = aE[X] + b$
3. $E[X + Y] = E[X] + E[Y]$ (Linearity of expectation)

---

## 2.2 Variance and Standard Deviation

**Variance** measures how far a set of numbers is spread out from their average value. It provides a measure of the dispersion or variability of the random variable around its mean. It is denoted by $Var(X)$, $\sigma^2$, or $V(X)$.

**Formula for Variance:**
$$ Var(X) = E[(X - \mu)^2] $$
An alternative and often easier computational formula is:
$$ Var(X) = E[X^2] - (E[X])^2 $$

### Calculating $E[X^2]$:
- **Discrete:** $E[X^2] = \sum_{x} x^2 \cdot p(x)$
- **Continuous:** $E[X^2] = \int_{-\infty}^{\infty} x^2 \cdot f(x) dx$

**Standard Deviation ($\sigma$):**
The standard deviation is the square root of the variance. It has the same units as the random variable, making it easier to interpret.
$$ \sigma = \sqrt{Var(X)} $$

**Properties of Variance:**
If $a$ and $b$ are constants:
1. $Var(c) = 0$ (The variance of a constant is $0$)
2. $Var(aX + b) = a^2 \cdot Var(X)$ (Adding a constant shifts the distribution but doesn't change the spread; multiplying by a constant scales the spread by the square of that constant)

---

## 2.3 Chebyshev’s Inequality

**Chebyshev’s inequality** guarantees that, for any probability distribution, "nearly all" values are close to the mean. It provides an upper bound on the probability that a random variable deviates significantly from its mean. It is useful because it applies to *any* distribution (discrete or continuous) as long as the mean and variance are defined.

**Statement:**
Let $X$ be a random variable with finite mean $\mu$ and finite, non-zero variance $\sigma^2$. Then for any real number $k > 0$:

$$ P(|X - \mu| \ge k) \le \frac{\sigma^2}{k^2} $$

Alternatively, expressing it in terms of standard deviations ($k = c\sigma$ for $c > 0$):
$$ P(|X - \mu| \ge c\sigma) \le \frac{1}{c^2} $$

This equivalent form states that the probability that a random variable differs from its mean by more than $c$ standard deviations is at most $1/c^2$.

**Complementary Form:**
The probability that a random variable falls *within* $k$ units of the mean is:
$$ P(|X - \mu| < k) \ge 1 - \frac{\sigma^2}{k^2} $$
or
$$ P(|X - \mu| < c\sigma) \ge 1 - \frac{1}{c^2} $$

**Example Application:**
If you want to know the probability that a value lies within $2$ standard deviations of the mean ($c=2$), Chebyshev's inequality guarantees that:
$P(|X - \mu| < 2\sigma) \ge 1 - \frac{1}{2^2} = 1 - \frac{1}{4} = \frac{3}{4} = 75\%$
Regardless of what the actual distribution looks like, at least 75% of the data must lie within 2 standard deviations of the mean.
