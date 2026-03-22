# 10. Queuing Models

This section outlines specific common queuing models based on Kendall's notation. In all formulas, we assume steady-state conditions where $\rho = \frac{\lambda}{\mu} < 1$.

---

## 10.1 Single Server, Infinite Capacity Model (M/M/1 : $\infty$/FCFS)

This is the most fundamental model.
- Poisson arrivals (rate $\lambda$)
- Exponential service times (rate $\mu$)
- 1 server
- Infinite system capacity.

**Formulas:**
1. **Utilization factor:** $\rho = \frac{\lambda}{\mu}$ (Probability that the server is busy).
2. **Prob. of $0$ customers in system (idle time):** $P_0 = 1 - \rho$
3. **Prob. of exactly $n$ customers in system:** $P_n = (1 - \rho)\rho^n$ or $P_n = \rho^n P_0$
4. **Prob. of system having $k$ or more customers:** $P(\ge k) = \rho^k$

**Performance Measures (using Little's Law):**
- **$L_s$** (Expected number in system):
  $$ L_s = \frac{\rho}{1 - \rho} = \frac{\lambda}{\mu - \lambda} $$
- **$L_q$** (Expected number in queue):
  $$ L_q = L_s - \frac{\lambda}{\mu} = \frac{\rho^2}{1 - \rho} = \frac{\lambda^2}{\mu(\mu - \lambda)} $$
- **$W_s$** (Expected waiting time in system):
  $$ W_s = \frac{L_s}{\lambda} = \frac{1}{\mu - \lambda} $$
- **$W_q$** (Expected waiting time in queue):
  $$ W_q = \frac{L_q}{\lambda} = \frac{\lambda}{\mu(\mu - \lambda)} $$

---

## 10.2 Single Server, Finite Capacity Model (M/M/1 : N/FCFS)

In this model, the system can hold a maximum of $N$ customers (including the one in service). If a customer arrives when there are $N$ customers in the system, they are turned away and lost.

Because the system is finite, the stability condition $\rho < 1$ is no longer strictly required for steady-state to exist, though $\rho \neq 1$ simplifies math.

**Formulas (Assuming $\rho = \lambda/\mu \neq 1$):**
1. **Prob. of $0$ customers in system:**
   $$ P_0 = \frac{1 - \rho}{1 - \rho^{N+1}} $$
2. **Prob. of exactly $n$ customers in system ($n \le N$):**
   $$ P_n = \rho^n P_0 = \frac{\rho^n(1 - \rho)}{1 - \rho^{N+1}} $$
3. **Prob. of system being full (also the fraction of customers lost):**
   $$ P_N = \frac{\rho^N(1 - \rho)}{1 - \rho^{N+1}} $$

**Effective Arrival Rate ($\lambda_{\text{eff}}$):**
Because customers arriving when the system is full are lost, the rate of customers actually *entering* the system is less than $\lambda$.
$$ \lambda_{\text{eff}} = \lambda(1 - P_N) = \mu(1-P_0) $$

**Performance Measures:**
- **$L_s$** (Expected number in system):
  $$ L_s = \frac{\rho}{1 - \rho} - \frac{(N+1)\rho^{N+1}}{1 - \rho^{N+1}} $$
  *(For computation, it's often easier to use $L_s = \sum_{n=0}^{N} n P_n$)*
- **$L_q$** (Expected number in queue):
  $$ L_q = L_s - (1 - P_0) $$
- **$W_s$ and $W_q$** (Must use effective lambda):
  $$ W_s = \frac{L_s}{\lambda_{\text{eff}}} $$
  $$ W_q = \frac{L_q}{\lambda_{\text{eff}}} $$

*(Note: If $\rho = 1$, then $P_0 = P_n = \frac{1}{N+1}$, and $L_s = \frac{N}{2}$)*

---

## 10.3 Multiple Server, Infinite Capacity Model (M/M/s : $\infty$/FCFS)

This model has $s$ parallel servers ($s > 1$) sharing a single queue.
- Poisson arrivals (rate $\lambda$)
- Exponential service times for each server (rate $\mu$ per server)
- Total maximum service capacity when all busy is $s\mu$.
- Stability condition: $\rho = \frac{\lambda}{s\mu} < 1$.

**Formulas:**
1. **Utilization factor per server:** $\rho = \frac{\lambda}{s\mu}$
2. **Prob. of 0 customers in system (all servers idle):**
   $$ P_0 = \left[ \sum_{n=0}^{s-1} \frac{(\lambda/\mu)^n}{n!} + \frac{(\lambda/\mu)^s}{s!(1 - \rho)} \right]^{-1} $$

3. **Prob. of exactly $n$ customers in system:**
   - If $0 \le n < s$ (some servers are idle):
     $$ P_n = \frac{(\lambda/\mu)^n}{n!} P_0 $$
   - If $n \ge s$ (all servers busy, queue is forming):
     $$ P_n = \frac{(\lambda/\mu)^n}{s! s^{n-s}} P_0 $$

4. **Probability of having to wait in queue (all servers busy):**
   This is the Erlang C formula, denoted $C(s, \lambda/\mu)$. It is the sum of probabilities $P_n$ for $n \ge s$.
   $$ P(\text{Waiting}) = P_{n \ge s} = \frac{(\lambda/\mu)^s}{s!(1 - \rho)} P_0 $$

**Performance Measures:**
- **$L_q$** (Expected number in queue):
  $$ L_q = P(\text{Waiting}) \cdot \frac{\rho}{1 - \rho} = \frac{P_0 (\lambda/\mu)^s \rho}{s!(1 - \rho)^2} $$
- **$L_s$** (Expected number in system):
  $$ L_s = L_q + \frac{\lambda}{\mu} $$
- **$W_q$** (Expected waiting time in queue):
  $$ W_q = \frac{L_q}{\lambda} $$
- **$W_s$** (Expected waiting time in system):
  $$ W_s = W_q + \frac{1}{\mu} $$
