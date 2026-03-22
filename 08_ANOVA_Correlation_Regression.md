# 8. ANOVA, Correlation, and Regression

## 8.1 Analysis of Variance (ANOVA) - One-Way Classification

**Analysis of Variance (ANOVA)** is a statistical technique used to compare the means of three or more independent groups or populations simultaneously to see if they are significantly different. It expands on the idea of the t-test, which compares only two means.

**One-way ANOVA** deals with one independent variable (factor) that has three or more levels (groups/treatments). The dependent variable must be continuous.

### Hypotheses
- $H_0: \mu_1 = \mu_2 = \mu_3 = \dots = \mu_k$ (All group means are equal)
- $H_1:$ At least one mean is different from the others.

### Key Concepts and the ANOVA Table
ANOVA partitions the total variation in the data into two components:
1. **Between-Groups Variance:** Variation due to the interaction between the samples (the effect of the treatments).
2. **Within-Groups Variance (Error):** Variation due to random error within each sample.

If the variance *between* groups is significantly larger than the variance *within* groups, we reject the null hypothesis.

**Notation:**
- $k$: Number of groups (treatments).
- $n_1, n_2, \dots, n_k$: Sample sizes of each group.
- $N = n_1 + n_2 + \dots + n_k$: Total total number of observations. ($N=kn$ if equal sample sizes).
- $T = \sum x_{ij}$: Grand total of all observations.
- Correction Factor ($CF$) = $\frac{T^2}{N}$

**Sums of Squares:**
1. Total Sum of Squares (TSS) = $\sum \sum x_{ij}^2 - CF$
2. Sum of Squares Between (SSB or SSTreatments) = $\sum \frac{T_i^2}{n_i} - CF$ (where $T_i$ is the total of the $i$-th group)
3. Sum of Squares Within (SSW or SSError) = TSS - SSB

**ANOVA Table Summary:**

| Source of Variation | Sum of Squares | Degrees of Freedom (df) | Mean Sum of Squares (Variance) | F-Ratio |
| :--- | :--- | :--- | :--- | :--- |
| Between Groups | $SSB$ | $v_1 = k - 1$ | $MSB = \frac{SSB}{k-1}$ | $F = \frac{MSB}{MSW}$ |
| Within Groups (Error) | $SSW$ | $v_2 = N - k$ | $MSW = \frac{SSW}{N-k}$ | |
| **Total** | $TSS$ | $N - 1$ | | |

If calculated $F > F_{\alpha}(v_1, v_2)$ (table value), we reject $H_0$.

---

## 8.2 Karl Pearson Coefficient of Correlation

**Correlation** measures the strength and direction of the linear relationship between two continuous variables. The most common measure is the **Karl Pearson Correlation Coefficient**, denoted by $r$.

**Properties of $r$:**
- $-1 \le r \le 1$
- If $r = 1$, perfect positive linear correlation.
- If $r = -1$, perfect negative linear correlation.
- If $r = 0$, no strictly linear relationship.
- $r$ is independent of the change of origin and scale.

**Formula:**
$$ r = \frac{\text{Covariance}(X,Y)}{\sqrt{Var(X) Var(Y)}} = \frac{\sum (x - \bar{x})(y - \bar{y})}{\sqrt{\sum (x - \bar{x})^2 \sum (y - \bar{y})^2}} $$

An alternative practical formula is:
$$ r = \frac{n \sum xy - (\sum x)(\sum y)}{\sqrt{[n \sum x^2 - (\sum x)^2][n \sum y^2 - (\sum y)^2]}} $$

---

## 8.3 Lines of Regression

**Regression** analysis is used to estimate or predict the unknown value of one variable (dependent variable) from the known value of another variable (independent variable). While correlation merely tells you if a relationship exists, regression provides a mathematical equation to use for prediction.

### Lines of Best Fit (Least Squares Method)
There are two regression lines based on which variable is independent:

**1. Regression Line of $Y$ on $X$:**
Use this line to predict values of $Y$ given $X$.
Equation: $Y = a + bX$
Or equivalently (in slope-intercept form based on means):
$$ y - \bar{y} = b_{yx} (x - \bar{x}) $$
Where $b_{yx}$ is the **Regression Coefficient of $Y$ on $X$** (the slope):
$$ b_{yx} = r \frac{\sigma_y}{\sigma_x} = \frac{\sum (x - \bar{x})(y - \bar{y})}{\sum (x - \bar{x})^2} $$

**2. Regression Line of $X$ on $Y$:**
Use this line to predict values of $X$ given $Y$.
Equation: $X = c + dY$
Or equivalently:
$$ x - \bar{x} = b_{xy} (y - \bar{y}) $$
Where $b_{xy}$ is the **Regression Coefficient of $X$ on $Y$** (the slope):
$$ b_{xy} = r \frac{\sigma_x}{\sigma_y} = \frac{\sum (x - \bar{x})(y - \bar{y})}{\sum (y - \bar{y})^2} $$

**Key Properties:**
- Both regression lines intersect at the point of their means: $(\bar{x}, \bar{y})$.
- The correlation coefficient $r$ is the geometric mean of the two regression coefficients:
  $r = \sqrt{b_{yx} \cdot b_{xy}}$ (with the correct sign appended).
- Both $b_{yx}$ and $b_{xy}$ share the same sign as $r$.
