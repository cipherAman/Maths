# 9. Queuing Theory Basics

## 9.1 Introduction and Concepts

**Queuing Theory** is the mathematical study of waiting lines (queues). A queue forms when a customer (or item/request) arrives at a service facility and the server is busy, forcing the customer to wait.

### Key Components of a Queuing System:
1. **Calling Population:** The source of customers (e.g., people, data packets, broken machines). It can be finite or infinite.
2. **Arrival Process:** How customers arrive at the system. Often modeled by a Poisson distribution (meaning inter-arrival times follow an Exponential distribution). The average arrival rate is denoted by $\lambda$ (lambda).
3. **Queue (Waiting Line):** The line where customers wait before being served. It can have a finite capacity (loss system) or infinite capacity.
4. **Queue Discipline:** The rule determining the order in which customers are served.
   - **FCFS / FIFO:** First Come First Served (most common).
   - **LCFS / LIFO:** Last Come First Served.
   - **SIRO:** Service in Random Order.
   - **Priority:** Serving based on a priority rule.
5. **Service Mechanism:** Consists of one or more servers. The time it takes to serve a customer is the service time, often modeled by an Exponential distribution. The average service rate per server is denoted by $\mu$ (mu).
6. **System Capacity:** The total number of customers that can be in the system (queue + service) at any given time.

### Applicability
Queuing theory is widely applied in telecommunications, traffic engineering, computing (CPU scheduling, disk I/O), factory design, hospital scheduling, and retail (supermarket checkouts).

---

## 9.2 Birth and Death Process

Many useful queuing models are special cases of the general **Birth and Death process**. It is a type of continuous-time Markov chain.
- **State ($n$):** The number of customers in the system at time $t$. Let $N(t) = n$.
- **Birth ($n \to n+1$):** corresponds to the arrival of a newly created customer into the system. The system transitions from state $n$ to state $n+1$. The birth rate at state $n$ is $\lambda_n$.
- **Death ($n \to n-1$):** corresponds to a customer completing service and leaving the system. The system transitions from state $n$ to state $n-1$. The death rate at state $n$ is $\mu_n$.

In small time intervals $\Delta t$:
1. A single birth occurs with probability $\lambda_n \Delta t + o(\Delta t)$.
2. A single death occurs with probability $\mu_n \Delta t + o(\Delta t)$.
3. No births and no deaths occur with probability $1 - (\lambda_n + \mu_n) \Delta t + o(\Delta t)$.
4. The probability of more than one event is negligible.

**Steady-State Probabilities:**
Let $P_n$ be the probability that there are $n$ customers in the system in the steady (equilibrium) state.
The balance equations dictate that the rate of entering state $n$ equals the rate of leaving state $n$:
$$ \text{Rate in} = \text{Rate out} $$
$$ \lambda_{n-1} P_{n-1} + \mu_{n+1} P_{n+1} = (\lambda_n + \mu_n) P_n $$

Solving these iteratively provides the general solution for steady-state probabilities:
$$ P_n = \frac{\lambda_0 \lambda_1 \dots \lambda_{n-1}}{\mu_1 \mu_2 \dots \mu_n} P_0 \quad \text{for } n = 1, 2, \dots $$
Where $P_0$ is found using the fact that the sum of all probabilities is $1$: $\sum_{n=0}^{\infty} P_n = 1$.

---

## 9.3 Poisson Queues

The most basic and widely used queuing models assume "Poisson arrivals" and "Exponential service times."
This is because:
1. **Poisson Arrivals:** The number of arrivals in a fixed time interval follows a Poisson distribution with mean parameter $\lambda t$. This mathematically equates to the time between consecutive arrivals following an **Exponential distribution** with mean $1/\lambda$.
2. **Exponential Service:** The time to serve a customer follows an Exponential distribution with mean $1/\mu$. This implies the service rate follows a Poisson process with parameter $\mu$.

The combination of Markovian (memoryless) exponential distributions makes the math manageable, hence these are highly popular "Poisson Queues" or Markovian Queues.

---

## 9.4 Kendall's Notation

Queuing models are classified using Kendall's notation: **(A/B/C) : (D/E/F)**
- **A:** Arrival process distribution (e.g., $M$ for Markovian/Poisson, $D$ for Deterministic, $G$ for General).
- **B:** Service time distribution (e.g., $M$, $D$, $G$).
- **C:** Number of parallel servers ($s = 1, 2, \dots, \infty$).
- **D:** Queue discipline (e.g., FCFS, SIRO). Often omitted if FCFS.
- **E:** Maximum system capacity (Finite $N$ or Infinite $\infty$).
- **F:** Size of calling population (Finite or Infinite $\infty$).

*Example:* **M/M/1 : $\infty$/FCFS** means Poisson arrivals ($M$), Exponential service times ($M$), Single server ($1$), Infinite system capacity ($\infty$), and First-Come-First-Served discipline (FCFS).

---

## 9.5 Characteristics (Performance Measures) of Queuing Models

To analyze the efficiency of a queue, we calculate specific performance measures. The standard symbols used are:

### Utilization Factor ($\rho$ - rho):
Also known as traffic intensity. It's the expected fraction of time the server is busy.
$$ \rho = \frac{\lambda}{s\mu} $$
(For a single server, $\rho = \frac{\lambda}{\mu}$). For the system to be stable (queue doesn't grow infinitely), we must have $\rho < 1$, i.e., average service rate must be greater than average arrival rate.

### Expected Number of Customers ($L$):
- **$L_s$:** Expected number of customers in the **System** (waiting + being served).
- **$L_q$:** Expected number of customers in the **Queue** (waiting only).
$$ L_s = L_q + \frac{\lambda}{\mu} $$

### Expected Waiting Time ($W$):
- **$W_s$:** Expected waiting time in the **System** for a customer (time in queue + time being served).
- **$W_q$:** Expected waiting time in the **Queue** for a customer.
$$ W_s = W_q + \frac{1}{\mu} $$

### Little's Formulas
These laws relate the number of customers ($L$) to the waiting times ($W$):
1. $L_s = \lambda W_s$
2. $L_q = \lambda W_q$

*(Note: $\lambda$ here represents the effective arrival rate into the system, which may be less than the actual arrival rate in finite-capacity loss systems).*
