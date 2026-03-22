# 4. Estimation of Parameters

## 4.1 Parameter and Statistic

In statistical inference, we aim to draw conclusions about a large population based on a smaller sample drawn from that population.

### What is a Parameter?
A **parameter** is a numerical value or characteristic that describes an entire population or a probability distribution. It is usually a fixed, often unknown, constant value.
- *Examples:* The population mean ($\mu$), population variance ($\sigma^2$), the proportion of successes in a population ($p$), or the rate parameter ($\lambda$) of an exponential distribution.

### What is a Statistic?
A **statistic** is a numerical value or characteristic calculated from a sample of data. It is a random variable, as its value depends on the particular sample chosen.
- *Examples:* The sample mean ($\bar{x}$ or $\hat{\mu}$), sample variance ($s^2$ or $\hat{\sigma}^2$), or the sample proportion ($\hat{p}$).

**The Goal of Estimation:**
The main goal of statistical estimation is to use a statistic (calculated from a sample) to estimate the unknown value of a parameter (belonging to the population).
The statistic used to estimate a parameter is called an **estimator** (e.g., sample mean $\bar{X}$ is an estimator for population mean $\mu$). The specific numerical value calculated from a given sample is the **estimate**.

---

## 4.2 Estimation Methods

There are several methods for finding estimators for unknown parameters. Two of the most common are:
1. **Method of Moments (MOM)**
2. **Maximum Likelihood Estimation (MLE)**

We will focus on the Maximum Likelihood Estimation method.

---

## 4.3 Maximum Likelihood Estimation (MLE)

**Maximum Likelihood Estimation (MLE)** is a method of estimating the parameters of a statistical model given observations. MLE seeks to find the parameter values that maximize the "likelihood function"—making the observed data the "most probable".

### The Concept
Suppose we have a set of independent and identically distributed (i.i.d.) observations $x_1, x_2, \dots, x_n$ drawn from a distribution with an unknown parameter $\theta$ (or a set of parameters). The probability of observing this specific sample given the parameter $\theta$ is represented by the joint PDF or PMF:

$$ f(x_1, x_2, \dots, x_n \mid \theta) = f(x_1 \mid \theta) \cdot f(x_2 \mid \theta) \cdots f(x_n \mid \theta) = \prod_{i=1}^{n} f(x_i \mid \theta) $$

When evaluating this joint probability as a function of the parameter $\theta$ for fixed data ($x_i$), we call it the **Likelihood Function ($L$)**.

$$ L(\theta \mid x_1, \dots, x_n) = \prod_{i=1}^{n} f(x_i \mid \theta) $$

**The Maximum Likelihood Estimator ($\hat{\theta}_{MLE}$)** is the value of $\theta$ that maximizes $L(\theta)$.

### Steps to Find the MLE ($\hat{\theta}$)

1. **Write the Likelihood Function $L(\theta)$:**
   Determine the joint probability distribution (or density) for the observed sample.
   $L(\theta) = \prod_{i=1}^{n} f(x_i \mid \theta)$

2. **Take the Natural Logarithm (Log-Likelihood):**
   Because products are harder to differentiate than sums, and because the natural logarithm is a monotonically increasing function (meaning it reaches its maximum at the same point as the original function), it is standard practice to maximize the log-likelihood function, $l(\theta)$ or $\ln L(\theta)$.
   $$ l(\theta) = \ln(L(\theta)) = \ln\left(\prod_{i=1}^{n} f(x_i \mid \theta)\right) = \sum_{i=1}^{n} \ln(f(x_i \mid \theta)) $$

3. **Differentiate the Log-Likelihood:**
   Take the derivative of the log-likelihood function with respect to the parameter $\theta$.
   $$ \frac{d}{d\theta} l(\theta) $$

4. **Set the Derivative to Zero and Solve:**
   Find the critical points by setting the derivative to zero. This equation is called the **likelihood equation**.
   $$ \frac{d}{d\theta} l(\theta) = 0 $$
   Solve for $\theta$. The solution naturally provides the maximum likelihood estimator $\hat{\theta}$.

5. **Verify it's a Maximum (Optional but good practice):**
   Check that the second derivative is negative at $\hat{\theta}$ to ensure it is a local maximum (though usually, the context guarantees this).
   $$ \left.\frac{d^2}{d\theta^2} l(\theta)\right|_{\theta=\hat{\theta}} < 0 $$

---

### Example: MLE for Poisson Distribution

Suppose a random sample $X_1, X_2, \dots, X_n$ is drawn from a Poisson distribution with unknown parameter $\lambda$. We want to find the MLE for $\lambda$.

**1. PMF of Poisson:**
$$ f(x \mid \lambda) = \frac{e^{-\lambda} \lambda^x}{x!} $$

**2. Likelihood Function $L(\lambda)$:**
$$ L(\lambda) = \prod_{i=1}^{n} \frac{e^{-\lambda} \lambda^{x_i}}{x_i!} = \frac{e^{-n\lambda} \lambda^{\sum x_i}}{\prod x_i!} $$

**3. Log-Likelihood Function $l(\lambda)$:**
$$ l(\lambda) = \ln\left(\frac{e^{-n\lambda} \lambda^{\sum x_i}}{\prod x_i!}\right) = -n\lambda + \left(\sum_{i=1}^{n} x_i\right) \ln(\lambda) - \ln\left(\prod_{i=1}^{n} x_i!\right) $$

**4. Differentiate with respect to $\lambda$:**
$$ \frac{d}{d\lambda} l(\lambda) = -n + \frac{\sum x_i}{\lambda} $$

**5. Set to Zero and Solve:**
$$ -n + \frac{\sum x_i}{\lambda} = 0 $$
$$ \frac{\sum x_i}{\lambda} = n $$
$$ \hat{\lambda} = \frac{\sum_{i=1}^{n} x_i}{n} = \bar{x} $$

**Conclusion:** The Maximum Likelihood Estimator for the Poisson parameter $\lambda$ is simply the sample mean $\bar{x}$.
