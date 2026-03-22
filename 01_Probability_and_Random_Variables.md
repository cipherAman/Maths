# 1. Probability and Random Variables

## 1.1 Introduction to Probability

**Probability** is a mathematical measure of the likelihood of an event occurring. It quantifies uncertainty and ranges between $0$ (impossible event) and $1$ (certain event).

### Key Terms:
- **Experiment:** Any procedure that can be infinitely repeated and has a well-defined set of possible outcomes. e.g., Tossing a coin.
- **Sample Space ($S$):** The set of all possible outcomes of an experiment. For a coin toss, $S = \{Head, Tail\}$.
- **Event ($E$):** A subset of the sample space. It is a specific outcome or a collection of outcomes.

### Axioms of Probability (Kolmogorov's Axioms):
1. For any event $E$, the probability of $E$ is non-negative: $P(E) \ge 0$.
2. The probability of the sample space is $1$: $P(S) = 1$.
3. If $E_1, E_2, \dots$ are mutually exclusive events (i.e., $E_i \cap E_j = \emptyset$ for $i \neq j$), then:
   $P(\bigcup_{i=1}^{\infty} E_i) = \sum_{i=1}^{\infty} P(E_i)$

---

## 1.2 Random Variables

A **Random Variable (RV)** is a function that assigns a real number to each outcome in the sample space of a random experiment. In simple terms, it maps the outcomes of an experiment to numbers. It is usually denoted by a capital letter, such as $X$, $Y$, or $Z$.

### Types of Random Variables:

1. **Discrete Random Variable:**
   A random variable is discrete if it can take on a countable number of distinct values. These values can be finite or countably infinite (like $0, 1, 2, \dots$).
   *Examples:*
   - Number of heads in 3 coin tosses: $X \in \{0, 1, 2, 3\}$.
   - Number of cars passing a toll booth in an hour.

2. **Continuous Random Variable:**
   A random variable is continuous if it can take any value within a given interval or range of real numbers. The number of possible values is uncountably infinite.
   *Examples:*
   - The exact height of students in a class.
   - The time it takes for a lightbulb to burn out.

---

## 1.3 Probability Functions

Probability functions describe the likelihood of a random variable taking on specific values or ranges of values.

### For Discrete Random Variables: Probability Mass Function (PMF)

The **Probability Mass Function (PMF)** gives the probability that a discrete random variable is exactly equal to some value. It is usually denoted as $p(x)$ or $P(X = x)$.

**Properties of PMF:**
1. $0 \le p(x) \le 1$ for all $x$.
2. $\sum_{all x} p(x) = 1$.

### For Continuous Random Variables: Probability Density Function (PDF)

The **Probability Density Function (PDF)** represents the relative likelihood for this random variable to take on a given value. For a continuous RV, the probability of it taking an *exact* specific point value is $0$. Therefore, we calculate the probability over an interval by integrating the PDF. It is denoted as $f(x)$.

**Properties of PDF:**
1. $f(x) \ge 0$ for all $x$.
2. $\int_{-\infty}^{\infty} f(x) dx = 1$.
3. $P(a \le X \le b) = \int_{a}^{b} f(x) dx$.

---

## 1.4 Cumulative Distribution Function (CDF)

The **Cumulative Distribution Function (CDF)**, denoted by $F(x)$, gives the probability that the random variable $X$ takes a value less than or equal to $x$. It applies to both discrete and continuous random variables.

$$ F(x) = P(X \le x) $$

### For Discrete Random Variables:
$$ F(x) = \sum_{t \le x} p(t) $$

### For Continuous Random Variables:
$$ F(x) = \int_{-\infty}^{x} f(t) dt $$

**Properties of CDF:**
1. **Non-decreasing:** If $a < b$, then $F(a) \le F(b)$.
2. **Bounds:** $\lim_{x \to -\infty} F(x) = 0$ and $\lim_{x \to \infty} F(x) = 1$.
3. **Right-Continuous:** $F(x)$ is continuous from the right.
4. **Relationship to PDF:** For a continuous random variable, the PDF is the derivative of the CDF: $f(x) = \frac{d}{dx}F(x)$.
5. **Interval Probability:** $P(a < X \le b) = F(b) - F(a)$.
