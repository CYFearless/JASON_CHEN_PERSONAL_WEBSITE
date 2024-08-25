## Lecture 2 Probability and Statistics Part 2

*Jason Chen YCHEN148@e.ntu.edu.sg* 

**Copyright Notice**

This document is a compilation of original notes by **Jason Chen** (YCHEN148@e.ntu.edu.sg). Unauthorized reproduction, downloading, or use for commercial purposes is strictly prohibited and may result in legal action. If you have any questions or find any content-related errors, please contact the author at the provided email address. The author will promptly address any necessary corrections.

### **I. Commonly Used Distributions-Discrete** 

---

#### 1<u>. Uniform Distribution $ U(a_1, \cdots, a_m) $</u>

This is a discrete uniform distribution where each outcome $ a_1, \cdots, a_m $ is equally likely. Let's analyze the components one by one.

**1.1 Probability Mass Function (PMF)**

The probability mass function (PMF) for the uniform distribution is given by:   $$ p(x) = \begin{cases} 
\frac{1}{m}, & x = a_1, \cdots, a_m \\
0, & \text{otherwise}
\end{cases} $$

<u>Explanation:</u> 

- The PMF states that the probability of any specific outcome $ x $ (from the set $ a_1, \cdots, a_m $) occurring is $ \frac{1}{m} $.
- If $ x $ is not one of the outcomes $ a_1, \cdots, a_m $, the probability is $ 0 $.

<u>Proof:</u> 
The uniform distribution assigns equal probability to each of the $ m $ possible outcomes. Since the sum of all probabilities must equal 1: $$ \sum_{i=1}^{m} p(a_i) = 1 $$; Since each outcome $ a_i $ has the same probability $ \frac{1}{m} $: $$ \sum_{i=1}^{m} \frac{1}{m} = \frac{m}{m} = 1 $$. This confirms that $ p(x) = \frac{1}{m} $ is the correct PMF.

**1.2 Moment Generating Function (MGF)**

The moment generating function (MGF) for the uniform distribution is given by: $$ \text{mgf}: M(t) = \frac{\sum_{j=1}^{m} e^{a_j t}}{m} $$

<u>Explanation:</u>

The MGF is used to find the moments of the distribution. The first moment (mean) and the second central moment (variance) can be derived from it.

<u>Proof:</u>
The MGF is defined as: $$ M(t) = \mathbb{E}[e^{tx}] = \sum_{j=1}^{m} p(a_j) e^{a_j t} = \sum_{j=1}^{m} \frac{1}{m} e^{a_j t} = \frac{\sum_{j=1}^{m} e^{a_j t}}{m} $$

**1.3 Mean (Expected Value)**

The mean (or expected value) $ \mu $ is given by: $$ \mu = \mathbb{E}[X] = \frac{\sum_{j=1}^{m} a_j}{m} \equiv \bar{a} $$

<u>Explanation:</u>

The mean of a uniform distribution is simply the average of all possible outcomes.

<u>Proof:</u>
The expected value is calculated as: $$ \mu = \mathbb{E}[X] = \sum_{j=1}^{m} p(a_j) a_j = \sum_{j=1}^{m} \frac{1}{m} a_j = \frac{\sum_{j=1}^{m} a_j}{m} $$

**1.4 Variance**

The variance $ \sigma^2 $ is given by: $$ \sigma^2 = \frac{\sum_{j=1}^{m} (a_j - \bar{a})^2}{m} $$

<u>Explanation:</u>

Variance measures the spread of the outcomes around the mean. It is the average of the squared differences from the mean.

<u>Proof:</u>
Variance is calculated as: $$ \sigma^2 = \mathbb{E}[(X - \mu)^2] = \mathbb{E}[X^2] - \mu^2 $$

Where: $$ \mathbb{E}[X^2] = \sum_{j=1}^{m} p(a_j) a_j^2 = \frac{\sum_{j=1}^{m} a_j^2}{m} $$; Therefore, the variance becomes: $$ \sigma^2 = \frac{\sum_{j=1}^{m} a_j^2}{m} - \left(\frac{\sum_{j=1}^{m} a_j}{m}\right)^2 = \frac{\sum_{j=1}^{m} (a_j - \bar{a})^2}{m}$$

**1.5 Parameter**

This indicates that the parameters $ a_i $ are real numbers, and there are $ m $ such parameters.

**1.6 Example**

**Throw a fair die once:** A classic example of a uniform distribution is rolling a fair six-sided die, where each face (1 through 6) has an equal probability of $ \frac{1}{6} $.

---

#### <u>**2. Bernoulli Distribution $ B(p) $**</u>

**2.1 Probability Mass Function (PMF)**

The probability mass function (PMF) for the Bernoulli distribution is given by: 

$p(x) = \begin{cases} 
p^x (1 - p)^{1 - x}, & \text{if } x = 0 \text{ or } x = 1 \\
0, & \text{otherwise}
\end{cases}$​

<u>Explanation:</u>

- When $ x = 1 $, the PMF is $ p $, representing the probability of success.
- When $ x = 0 $, the PMF is $ 1 - p $, representing the probability of failure.

<u>Proof:</u>
The PMF for a Bernoulli random variable can be written as: $p(x) = p^x (1 - p)^{1 - x}$

This expression works for both cases:

- If $ x = 1 $, $ p(1) = p^1 (1 - p)^0 = p $.
- If $ x = 0 $, $ p(0) = p^0 (1 - p)^1 = 1 - p $.

The sum of the probabilities for all possible outcomes must equal 1: $p(1) + p(0) = p + (1 - p) = 1$

**2.2 Moment Generating Function (MGF)**

The moment generating function (MGF) for the Bernoulli distribution is given by: $\text{mgf}: M(t) = p e^t + 1 - p$

<u>Explanation:</u>

- The MGF helps us find the moments of the distribution, like the mean and variance.

<u>Proof:</u>
The MGF is defined as: $M(t) = \mathbb{E}[e^{tx}] = p e^{t \cdot 1} + (1 - p) e^{t \cdot 0} = p e^t + (1 - p)$.  This function can be used to derive the mean and variance of the distribution.

**2.3 Mean (Expected Value)**

The mean (or expected value) $ \mu $ for the Bernoulli distribution is: $\mu = \mathbb{E}[X] = p$

<u>Explanation:</u>

The mean represents the probability of success in a Bernoulli trial.

<u>Proof:</u>
The expected value is calculated as: $\mu = \mathbb{E}[X] = p \cdot 1 + (1 - p) \cdot 0 = p$

**2.4 Variance**

The variance $ \sigma^2 $ for the Bernoulli distribution is: $\sigma^2 = p(1 - p)$

<u>Explanation:</u>

The variance measures the spread of the outcomes around the mean. It reaches its maximum when $ p = 0.5 $, indicating the highest uncertainty.

<u>Proof:</u>
Variance is calculated using the formula: $\sigma^2 = \mathbb{E}[X^2] - \mu^2$

Since $ X^2 = X $ for $ X $ being either 0 or 1: $\mathbb{E}[X^2] = p$

Thus, the variance becomes: $\sigma^2 = p - p^2 = p(1 - p)$

**2.5 Parameter**

$ p \in [0, 1] $: $ p $ is the probability of success in a Bernoulli trial and lies between 0 and 1.

**2.6 Example**

Toss a coin once, $ p $ = probability that head occurs:  A typical example is a coin toss, where $ p $ represents the probability of getting heads.

**If $ A $ is an event, then the indicator random variable $ I_A $ follows the Bernoulli distribution.**

An indicator variable $ I_A $ takes the value 1 if event $ A $ occurs and 0 otherwise, which follows a Bernoulli distribution with parameter $ p = \mathbb{P}(A) $.

---

#### <u>**3. Binomial Distribution \( B(n, p) \)**</u>

The binomial distribution describes the number of successes in $n$ independent Bernoulli trials, where each trial has a probability $p$ of success. The parameters $n$ and $p$ define the distribution.

**3.1 Probability Mass Function (PMF)**

The probability mass function (pmf) for the binomial distribution is given by:

$p(x) = \begin{cases} 
\binom{n}{x} p^x (1 - p)^{n - x}, & x = 0, 1, \dots, n \\
0, & \text{otherwise}
\end{cases}$

<u>Explanation:</u>

- $\binom{n}{x}$ is the binomial coefficient, representing the number of ways to choose $x$ successes out of $n$ trials.
- $p^x$ is the probability of $x$ successes.
- $(1 - p)^{n - x}$ is the probability of $n - x$ failures.

<u>Proof:</u>
The pmf can be derived as the product of the probability of a specific sequence of $x$ successes and $n - x$ failures, multiplied by the number of such sequences:

$p(x) = \binom{n}{x} p^x (1 - p)^{n - x}$     Where $\binom{n}{x} = \frac{n!}{x!(n-x)!}$ is the binomial coefficient.

**3.2 Moment Generating Function (MGF)**

The moment generating function (MGF) for the binomial distribution is:

$\text{mgf}: M(t) = \left(p e^t + 1 - p\right)^n$

<u>Explanation:</u>

- The MGF is a powerful tool for finding the moments of the distribution, such as the mean and variance.

<u>Proof:</u>
The MGF for a binomial distribution can be derived by recognizing that the binomial distribution is the sum of $n$ independent Bernoulli random variables:

$M(t) = \mathbb{E}\left[e^{tX}\right] = \mathbb{E}\left[\prod_{i=1}^{n} e^{tX_i}\right] = \left(\mathbb{E}\left[e^{tX_i}\right]\right)^n = \left(p e^t + 1 - p\right)^n$; Here, $X_i$ represents the individual Bernoulli trials.

**3.3 Mean (Expected Value)**

The mean (or expected value) $\mu$ for the binomial distribution is:

$\mu = \mathbb{E}[X] = np$

<u>Explanation:</u>

The mean represents the expected number of successes in $n$ trials.

<u>Proof:</u>
The mean can be derived from the sum of the expected values of $n$ Bernoulli trials:

$\mu = \mathbb{E}\left[\sum_{i=1}^{n} X_i\right] = \sum_{i=1}^{n} \mathbb{E}[X_i] = np$

**3.4 Variance**

The variance $\sigma^2$ for the binomial distribution is: $\sigma^2 = np(1 - p)$

<u>Explanation:</u>

The variance measures the spread of the number of successes around the mean.

<u>Proof:</u>
The variance of a sum of independent Bernoulli trials is the sum of the variances of the individual trials:

$\sigma^2 = \mathbb{V}\left[\sum_{i=1}^{n} X_i\right] = \sum_{i=1}^{n} \mathbb{V}[X_i] = np(1 - p)$

Where $\mathbb{V}[X_i] = p(1 - p)$ is the variance of a single Bernoulli trial.

**3.5 Parameter**

Parameter $p \in [0, 1]$ and $n = 1, 2, \dots$:

- $p$ is the probability of success in a single trial.
- $n$ is the number of trials.

**3.6 Example**

Number of heads when tossing a coin $n$ times: If you toss a fair coin $n$ times, the number of heads (successes) follows a binomial distribution with $n$ trials and $p = 0.5$.

- **Binomial Theorem:** The formula $(a + b)^n = \sum_{x=0}^{n} \binom{n}{x} a^x b^{n-x}$ underpins the binomial distribution.
- **Application in Finance:** The binomial distribution is commonly used in security price modeling, assuming that the price can either rise or fall by a fixed amount during small intervals of time.

Let's break down the problem presented in the slide, which deals with a one-period binomial model for stock pricing. We'll work through the problem step by step to ensure we have the correct solution.

**Problem Statement**

We are dealing with a stock market model at time $t = 0$ where there are two investment opportunities:

<u>Purchase and (short-) selling of stocks:</u>

- Current price: $P_1(0) = p_1 > 0$
- Future price $X(T)$ at time $T$: $X(T) = \begin{cases} 
  f \cdot e^{rT} + g \cdot p_1 \cdot u, & \text{with probability } p \\
  f \cdot e^{rT} + g \cdot p_1 \cdot d, & \text{with probability } 1 - p 
  \end{cases}$​
- $u > d$: Here, $u$ and $d$ represent the up and down factors of the stock price.
- $(f, g)$ is the trading strategy:
  - $f$: The face amount invested.
  - $g$: The number of stocks kept at $t = 0$. If $g$ is negative, it indicates a short sale.

<u>Fixed deposit or loan:</u>

- Interest rate: $r \geq 0$
- Continuous return over time frame $[0, T]$: $P_0(0) = 1, \quad P_0(T) = e^{rT}$
- This represents the capital development of a monetary unit.

**Step-by-Step Solution**

<u>Analyzing the Trading Strategy</u>

The future value $X(T)$ at time $T$ is dependent on the trading strategy $(f, g)$:

- If the stock price moves up (with probability $p$): $X(T) = f \cdot e^{rT} + g \cdot p_1 \cdot u$
- If the stock price moves down (with probability $1 - p$): $X(T) = f \cdot e^{rT} + g \cdot p_1 \cdot d$

- $f$ represents the amount of money invested in the risk-free asset (e.g., bond).
- $g$ represents the amount of stock held (positive $g$) or shorted (negative $g$).

<u>Risk-Neutral Valuation</u>

In a one-period binomial model, the price of a derivative or a contingent claim can be computed using risk-neutral valuation. The risk-neutral probability $q$ is defined as: $q = \frac{e^{rT} - d}{u - d}$

The expected value of the future price $X(T)$ under the risk-neutral measure is: $\mathbb{E}^\mathbb{Q}[X(T)] = q \cdot (f \cdot e^{rT} + g \cdot p_1 \cdot u) + (1 - q) \cdot (f \cdot e^{rT} + g \cdot p_1 \cdot d)$

The present value $X(0)$ at time $t = 0$ should equal the discounted expected future value: $X(0) = \frac{1}{e^{rT}} \mathbb{E}^\mathbb{Q}[X(T)]$

Given $P_0(0) = 1$ and $P_0(T) = e^{rT}$, the price at time $t = 0$ becomes: $X(0) = \frac{q \cdot f \cdot e^{rT} + q \cdot g \cdot p_1 \cdot u + (1 - q) \cdot f \cdot e^{rT} + (1 - q) \cdot g \cdot p_1 \cdot d}{e^{rT}}$

Simplifying this expression gives the initial capital required.

Given that the number of upward movements in the stock price follows a $B(1, p)$-distributed random variable, it means:

- With probability $p$, the stock price moves up.
- With probability $1 - p$, the stock price moves down.

---

#### <u>**4. Poisson Distribution $P(\lambda)$ - Limit of Binomial Distribution**</u>

Certainly! Let's go through the content in the previous two images step by step, providing detailed explanations and proofs for each component, similar to how we did with the Poisson distribution.

**Understanding the Transition from Binomial to Poisson Distribution**

**Step 1: Start with the Binomial PMF**

The binomial distribution for a random variable $X_n \sim B(n, p_n)$ is given by: $P(X_n = x) = \binom{n}{x} p_n^x (1 - p_n)^{n - x}$

- $n$ is the number of trials
- $p_n$ is the probability of success in each trial
- $x$ is the number of successes in $n$ trials

**Step 2: Transition to Poisson**

Consider the case where $n$ becomes very large ($n \to \infty$) and $p_n$ becomes very small ($p_n \to 0$) such that $\lambda = n p_n$ remains constant. In this scenario, the binomial distribution can be approximated by the Poisson distribution.

We start by rewriting the binomial pmf using this condition: $P(X_n = x) = \binom{n}{x} \left(\frac{\lambda}{n}\right)^x \left(1 - \frac{\lambda}{n}\right)^{n - x}$

- The binomial coefficient $\binom{n}{x}$ is given by: $\binom{n}{x} = \frac{n(n-1)\dots(n-x+1)}{x!}$

  As $n$ becomes large, this simplifies to: $\frac{n(n-1)\dots(n-x+1)}{n^x} \approx 1$

- The probability of success term $p_n^x$ becomes: $\left(\frac{\lambda}{n}\right)^x$

- The term $(1 - p_n)^{n-x}$ can be approximated using the exponential function: $\left(1 - \frac{\lambda}{n}\right)^{n-x} \approx e^{-\lambda}$


Thus, the binomial pmf transitions to the Poisson pmf as: $\lim_{n \to \infty} P(X_n = x) = \frac{\lambda^x e^{-\lambda}}{x!}$

This is the Poisson distribution with parameter $\lambda = np_n$​.

The formula shown in the second image is a well-known limit in calculus:

$\lim_{n \to \infty} \left(1 + \frac{a_n}{n}\right)^n = e^{a}$

This result is a fundamental identity used in the derivation of the exponential function and is central to many proofs in probability and calculus.

<u>Explanation:</u>

- **Intuition:** This limit expresses the idea that as $n$ becomes very large, the expression $\left(1 + \frac{a_n}{n}\right)^n$ approaches $e^a$. The parameter $a_n$ converges to some constant $a$ as $n$ increases.

- **Connection to Exponentials:** This result shows how exponential growth can be approximated by a sequence of compounding steps. The expression $\left(1 + \frac{a_n}{n}\right)^n$ is a discrete approximation of the continuous exponential function.

- **Applications:** This limit is often used in proofs related to the convergence of binomial distributions to Poisson distributions, the derivation of compound interest formulas, and the calculation of certain types of sums and integrals.

**4.1 Probability Mass Function (PMF):**

$p(x) = \frac{\lambda^x e^{-\lambda}}{x!}, \quad x = 0, 1, 2, \dots$

This is derived as shown above, representing the probability of $x$ events occurring in a fixed interval.

**4.2 Moment Generating Function (MGF):**

The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}]$.   For Poisson distribution, we have: $M_X(t) = \sum_{x=0}^{\infty} e^{tx} \cdot \frac{\lambda^x e^{-\lambda}}{x!}$

Simplifying using the series expansion of the exponential function: $M_X(t) = e^{\lambda(e^t - 1)}$

**4.3 Mean (Expected Value):**

$\mathbb{E}[X] = \lambda$   The mean is simply $\lambda$​, representing the average number of events in the interval.

The expected value (mean) $\mathbb{E}[X]$ for a Poisson distribution is: $\mathbb{E}[X] = \sum_{x=0}^{\infty} x \cdot P(X = x) = \sum_{x=0}^{\infty} x \cdot \frac{\lambda^x e^{-\lambda}}{x!}$

By simplifying this using the properties of sums and derivatives: $\mathbb{E}[X] = \lambda$​

**4.4 Variance:**

$\text{Var}(X) = \lambda$​

$\mathbb{E}[X^2] = \sum_{x=0}^{\infty} x^2 \cdot P(X = x) = \sum_{x=0}^{\infty} x^2 \cdot \frac{\lambda^x e^{-\lambda}}{x!}$

We can rewrite $x^2$ as $x(x-1) + x$: $\mathbb{E}[X^2] = \sum_{x=0}^{\infty} x(x-1) \cdot \frac{\lambda^x e^{-\lambda}}{x!} + \sum_{x=0}^{\infty} x \cdot \frac{\lambda^x e^{-\lambda}}{x!}$

The first term $\sum_{x=0}^{\infty} x(x-1) \cdot \frac{\lambda^x e^{-\lambda}}{x!}$ simplifies to: $\sum_{x=2}^{\infty} \frac{\lambda^2 \cdot \lambda^{x-2} e^{-\lambda}}{(x-2)!} = \lambda^2$

The second term $\sum_{x=0}^{\infty} x \cdot \frac{\lambda^x e^{-\lambda}}{x!}$ is just the expected value $\mathbb{E}[X]$, which is $\lambda$.

Thus: $\mathbb{E}[X^2] = \lambda^2 + \lambda$; Finally, the variance $\text{Var}(X)$ is: $\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = (\lambda^2 + \lambda) - \lambda^2 = \lambda$

**4.5 Parameter:**

$\lambda > 0$: $\lambda$ is the rate parameter, indicating the expected number of occurrences in a given time or space interval.

**4.6 Example:**

**Number of phone calls coming into an exchange during a unit of time:**

If $\lambda$ represents the average number of calls per hour, the number of calls in a given hour follows a Poisson distribution with parameter $\lambda$.

**Summation of Independent Poisson Random Variables**

If $X_i \sim P(\lambda_i)$ are independent, then their sum: $Y = X_1 + \dots + X_k \sim P(\lambda_1 + \dots + \lambda_k)$

This means the sum of independent Poisson-distributed variables is also Poisson-distributed, with the rate parameter being the sum of individual rate parameters.

**Proof of the Summation of Independent Poisson Random Variables**

**Statement:** If $X_i \sim P(\lambda_i)$ are independent Poisson random variables, then their sum $Y = X_1 + \dots + X_k$ is also Poisson-distributed with rate parameter $\lambda = \lambda_1 + \dots + \lambda_k$.

<u>Definition of Poisson Distribution:</u>
A random variable $X$ is said to follow a Poisson distribution with rate parameter $\lambda$ if its probability mass function (PMF) is given by: $P(X = x) = \frac{\lambda^x e^{-\lambda}}{x!}, \quad x = 0, 1, 2, \dots$

<u>2. Moment Generating Function (MGF):</u>
The moment generating function (MGF) of a Poisson random variable $X \sim P(\lambda)$ is: $M_X(t) = \mathbb{E}[e^{tX}] = \sum_{x=0}^{\infty} e^{tx} \frac{\lambda^x e^{-\lambda}}{x!} = e^{\lambda(e^t - 1)}$

<u>3. MGF of the Sum:</u>
Let $Y = X_1 + X_2 + \dots + X_k$. The MGF of $Y$ is the product of the MGFs of the independent $X_i$: $M_Y(t) = M_{X_1}(t) \cdot M_{X_2}(t) \cdot \dots \cdot M_{X_k}(t)$

Substituting the MGF of each $X_i$: $M_Y(t) = e^{\lambda_1(e^t - 1)} \cdot e^{\lambda_2(e^t - 1)} \cdot \dots \cdot e^{\lambda_k(e^t - 1)}$

Simplifying the expression: $M_Y(t) = e^{(\lambda_1 + \lambda_2 + \dots + \lambda_k)(e^t - 1)} = e^{\lambda(e^t - 1)}$; where $\lambda = \lambda_1 + \lambda_2 + \dots + \lambda_k$.

---

#### <u>5. Negative Binomial Distribution $NB(r, p)$</u>

The negative binomial distribution describes the number of trials $X$ required to achieve the $r$th success in a sequence of independent Bernoulli trials, where each trial has a probability $p$ of success.

**5.1 Probability Mass Function (PMF)**

The PMF for the negative binomial distribution is given by:

$p(x) = \begin{cases} 
\binom{x-1}{x-r} p^r (1 - p)^{x-r}, & x = r, r+1, \dots \\
0, & \text{otherwise}
\end{cases}$

- $x$ is the total number of trials needed to achieve the $r$th success.
- $p$ is the probability of success on each trial.
- $(1 - p)$ is the probability of failure on each trial.

Derivation of the PMF:

1. Number of Failures: Before the $r$th success, there must be $x - r$ failures.

2. Success-Failure Pattern: The probability of having $x - r$ failures and $r$ successes (with the last trial being a success) is: $p(x) = \binom{x-1}{r-1} p^r (1-p)^{x-r}$

The binomial coefficient $\binom{x-1}{r-1}$ represents the number of ways to arrange $x-1$ trials into $r-1$ successes and $x-r$ failures, followed by the final success.

**5.2 Moment Generating Function (MGF)**

The MGF $M_X(t)$ for the negative binomial distribution is given by: $M_X(t) = \left(\frac{p e^t}{1 - (1-p) e^t}\right)^r, \quad \text{for } t < -\log(1-p)$

Derivation of the MGF:

1. The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}]$

2. By summing over all possible values of $X$: $M_X(t) = \sum_{x=r}^{\infty} e^{tx} \binom{x-1}{r-1} p^r (1-p)^{x-r}$

3. This series is simplified using the sum of a geometric series, leading to the compact form:

$M_X(t) = \left(\frac{p e^t}{1 - (1-p) e^t}\right)^r$;    This function is valid as long as $t < -\log(1-p)$ to ensure convergence.

**5.3 Mean**

The mean $\mathbb{E}[X]$ of the negative binomial distribution is given by: $\mathbb{E}[X] = \frac{r}{p}$

<u>Derivation of the Mean:</u>  

From the definition of expectation: $\mathbb{E}[X] = \sum_{x=r}^{\infty} x \cdot \binom{x-1}{r-1} p^r (1-p)^{x-r}$ ; This sum can be calculated directly or derived using the MGF by taking the first derivative with respect to $t$ and evaluating at $t = 0$: $\mathbb{E}[X] = \frac{dM_X(t)}{dt} \Bigg|_{t=0} = \frac{r}{p}$

**5.4 Variance**

The variance $\text{Var}(X)$ of the negative binomial distribution is given by: $\text{Var}(X) = \frac{r(1-p)}{p^2}$

Derivation of the Variance: The variance is given by: $\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$

The second moment $\mathbb{E}[X^2]$ can be calculated by taking the second derivative of the MGF: $\text{Var}(X) = \frac{d^2M_X(t)}{dt^2} \Bigg|_{t=0} - \left(\frac{r}{p}\right)^2$ $= \text{Var}(X) = \frac{r(1-p)}{p^2}$

**5.5 Parameter Range:**

- $p \in [0, 1]$: Probability of success in each trial.
- $r = 1, 2, \dots$: The number of successes being targeted.

**5.6 Example:**

Lottery: If a person must purchase tickets until they achieve the $r$th winning ticket, the total number of tickets bought follows a negative binomial distribution.

Let's break down the **Hypergeometric distribution $HG(r, n, m)$**, explaining each component step by step, including the probability mass function (PMF), mean, variance, and the relationship to the binomial distribution.

---

#### <u>6. Hypergeometric Distribution $HG(r, n, m)$</u>

**6.1 Probability Mass Function (PMF)**

The PMF of the hypergeometric distribution is given by: $p(x) = \frac{\binom{n}{x} \binom{m}{r-x}}{\binom{n+m}{r}}, \quad x = 0, 1, \dots, \min(r, n), \text{ and } r-x \leq m$

- $n$ is the number of black balls.
- $m$ is the number of white balls.
- $r$ is the total number of balls drawn without replacement.
- $x$ is the number of black balls drawn.

Derivation of the PMF:

1. Combination Calculation: The number of ways to draw $x$ black balls from $n$ black balls is given by $\binom{n}{x}$. Similarly, the number of ways to draw $r-x$ white balls from $m$ white balls is $\binom{m}{r-x}$.

2. Total Combinations: The total number of ways to draw $r$ balls from $n + m$ balls (black and white) is $\binom{n+m}{r}$.

3. PMF Expression: The probability of drawing exactly $x$ black balls in $r$ draws is then the ratio of the favorable outcomes to the total outcomes: $p(x) = \frac{\binom{n}{x} \binom{m}{r-x}}{\binom{n+m}{r}}$

**6.2 Moment Generating Function (MGF)**

The hypergeometric distribution does not have an explicit closed-form moment generating function (MGF). This is because the lack of replacement complicates the analysis of the moments in a way that precludes a simple closed-form expression.

**6.3 Mean**

The mean $\mathbb{E}[X]$ of the hypergeometric distribution is given by: $\mathbb{E}[X] = \frac{r \cdot n}{n + m}$

Derivation of the Mean:

1. The mean is derived from the linearity of expectation. Since the hypergeometric distribution models the number of successes (black balls) drawn, the expected value is proportional to the fraction of the total balls that are black.

2. $n$ is the number of black balls, and $n + m$ is the total number of balls. Thus, the mean number of black balls drawn is: $\mathbb{E}[X] = r \cdot \frac{n}{n+m}$

**6.4 Variance**

The variance $\text{Var}(X)$ of the hypergeometric distribution is given by: $\text{Var}(X) = \frac{r \cdot n \cdot m \cdot (n+m-r)}{(n+m)^2 \cdot (n+m-1)}$

Derivation of the Variance:

1. Variance accounts for both the proportion of successes and the finite size of the population.

2. The formula takes into consideration the fact that the draws are without replacement, which introduces negative dependence between the draws (i.e., drawing one black ball decreases the probability of drawing another black ball).

3. The variance formula is derived from the second moment and adjusted for the non-independence of the draws: $\text{Var}(X) = r \cdot \frac{n}{n+m} \cdot \frac{m}{n+m} \cdot \frac{n+m-r}{n+m-1}$

**6.5 Parameters**

- $r$: The number of draws.
- $n$: The number of black balls.
- $m$: The number of white balls.
- $r \leq n + m$: The number of draws cannot exceed the total number of balls.

**6.6 Example:**

**Sampling Industrial Products:** If you want to determine the number of defective items (black balls) in a sample drawn from a batch without replacement, the hypergeometric distribution models the probability of finding a specific number of defective items.

**Relationship to Binomial Distribution**

The hypergeometric distribution can be related to the binomial distribution as the population size becomes large:

$\binom{n}{x} \binom{m}{r-x} / \binom{n+m}{r} \rightarrow \binom{r}{x} p^x (1-p)^{r-x}$

Where: $p = \frac{n}{n+m}$ is the probability of success in each draw.

This approximation holds under the condition that $n, m \to \infty$ while maintaining a fixed ratio.

---

### **II. Commonly Used Distributions-Discrete** 

---

#### <u>1. Uniform Distribution $U(a, b)$</u>

**1.1 Probability Density Function (PDF)**

The PDF of the uniform distribution $U(a, b)$ is given by: $f(x) = \begin{cases} 
\frac{1}{b-a}, & \text{if } a \leq x \leq b \\
0, & \text{otherwise}
\end{cases}$

<u>Derivation of the PDF:</u>

* Uniformity Condition: Since the distribution is uniform, every point within the interval $[a, b]$ must have the same probability density. This implies that the density $f(x)$ is constant over this interval.

* Total Probability: The total area under the PDF curve must be 1,  $\int_a^b f(x) \, dx = 1$

* Solving for $f(x)$: $f(x) \cdot (b - a) = 1 \quad \Rightarrow \quad f(x) = \frac{1}{b-a}$ 

* Thus, within the interval $[a, b]$, the PDF is $ \frac{1}{b-a} $, and outside this interval, the PDF is 0.

**1.2 Cumulative Distribution Function (CDF)**

The CDF $F(x)$ of the uniform distribution is given by: $F(x) = \begin{cases} 
0, & \text{if } x < a \\
\frac{x-a}{b-a}, & \text{if } a \leq x \leq b \\
1, & \text{if } x > b
\end{cases}$

Derivation of the CDF:

* Definition: The CDF is the probability that a random variable $X$ takes a value less than or equal to $x$: $F(x) = P(X \leq x)$

* For $x < a$: The probability is 0 since $x$ is outside the interval: $F(x) = 0$

* For $a \leq x \leq b$: The probability is the area under the PDF curve from $a$ to $x$: $F(x) = \int_a^x \frac{1}{b-a} \, du = \frac{x-a}{b-a}$

* For $x > b$: The probability is 1, as $x$ is beyond the upper limit of the interval: $F(x) = 1$

**1.3 Moment Generating Function (MGF)**

The MGF $M_X(t)$ of the uniform distribution $U(a, b)$ is given by: $M_X(t) = \frac{e^{bt} - e^{at}}{t(b-a)}, \quad t \in \mathbb{R}$

Derivation of the MGF:

* Definition: The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} f(x) \, dx$

2. Applying the PDF: $M_X(t) = \int_a^b e^{tx} \cdot \frac{1}{b-a} \, dx$

3. Integration: $M_X(t) = \frac{1}{b-a} \int_a^b e^{tx} \, dx = \frac{1}{b-a} \cdot \frac{e^{tx}}{t} \Big|_a^b$

4. Simplifying: $M_X(t) = \frac{e^{bt} - e^{at}}{t(b-a)}$

**1.4 Mean**

The mean $ \mathbb{E}[X] $ of the uniform distribution is given by: $\mathbb{E}[X] = \frac{a + b}{2}$

Derivation of the Mean:

* Definition: The mean is the expected value of $X$: $\mathbb{E}[X] = \int_{-\infty}^{\infty} x f(x) \, dx$

2. Applying the PDF: $\mathbb{E}[X] = \int_a^b x \cdot \frac{1}{b-a} \, dx$

3. Integration: $\mathbb{E}[X] = \frac{1}{b-a} \cdot \frac{x^2}{2} \Big|_a^b = \frac{1}{b-a} \cdot \frac{b^2 - a^2}{2}$

4. Simplifying: $\mathbb{E}[X] = \frac{b+a}{2}$

**1.5 Variance**

The variance $\text{Var}(X)$ of the uniform distribution is given by: $\text{Var}(X) = \frac{(b-a)^2}{12}$

Derivation of the Variance:

* Definition: The variance is the second central moment: $\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$

* First, calculate $ \mathbb{E}[X^2] $: $\mathbb{E}[X^2] = \int_a^b x^2 \cdot \frac{1}{b-a} \, dx = \frac{1}{b-a} \cdot \frac{x^3}{3} \Big|_a^b = \frac{b^3 - a^3}{3(b-a)}$

* Simplifying $ \mathbb{E}[X^2] $: $\mathbb{E}[X^2] = \frac{b^2 + ab + a^2}{3}$

* Subtracting the square of the mean: $\text{Var}(X) = \mathbb{E}[X^2] - \left(\frac{b+a}{2}\right)^2 = \frac{b^2 + ab + a^2}{3} - \frac{b^2 + 2ab + a^2}{4}$

* Final Simplification: $\text{Var}(X) = \frac{(b-a)^2}{12}$​

---

#### 2. Exponential Distribution $EXP(\lambda)$

The exponential distribution is commonly used to model the time between events in a Poisson process, such as the time between arrivals in a queue or the time until a component fails.

**2.1 Probability Density Function (PDF)**

The PDF of the exponential distribution $EXP(\lambda)$ is given by: $f(x) = \begin{cases} 
\lambda e^{-\lambda x}, & \text{if } x \geq 0 \\
0, & \text{if } x < 0
\end{cases}$

Derivation of the PDF:

* Memorylessness Property: The exponential distribution is characterized by the memoryless property, meaning that the probability of an event occurring in the future is independent of the past.

* Poisson Process: If events occur according to a Poisson process with rate $\lambda$, the time $X$ until the first event occurs follows an exponential distribution. The PDF represents the rate at which the events occur.

* Normalization: The PDF must integrate to 1 over the range $[0, \infty)$: $\int_0^{\infty} \lambda e^{-\lambda x} \, dx = 1$​

**2.2 Cumulative Distribution Function (CDF)**

The CDF $F(x)$ of the exponential distribution is given by: $F(x) = \begin{cases} 
1 - e^{-\lambda x}, & \text{if } x \geq 0 \\
0, & \text{if } x < 0
\end{cases}$

Derivation of the CDF:

* Definition: The CDF is the probability that the random variable $X$ takes a value less than or equal to $x$: $F(x) = P(X \leq x) = \int_{-\infty}^x f(u) \, du$

* For $x < 0$: The probability is 0 since $X$ cannot take negative values in the exponential distribution: $F(x) = 0$

* For $x \geq 0$: The probability is the integral of the PDF from 0 to $x$: $F(x) = \int_0^x \lambda e^{-\lambda u} \, du = 1 - e^{-\lambda x}$

**2.3 Moment Generating Function (MGF)**

The MGF $M_X(t)$ of the exponential distribution $EXP(\lambda)$ is given by: $M_X(t) = \frac{\lambda}{\lambda - t}, \quad t < \lambda$

Derivation of the MGF:

* Definition: The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} f(x) \, dx$

2. Applying the PDF: $M_X(t) = \int_0^{\infty} e^{tx} \lambda e^{-\lambda x} \, dx = \lambda \int_0^{\infty} e^{-(\lambda - t)x} \, dx$

3. Integration: $M_X(t) = \lambda \cdot \frac{1}{\lambda - t}, \quad \text{for } t < \lambda$    This condition $t < \lambda$ ensures the integral converges.

**2.4 Mean**

The mean $\mathbb{E}[X]$ of the exponential distribution is given by: $\mathbb{E}[X] = \frac{1}{\lambda}$

Derivation of the Mean:

* Definition: The mean is the expected value of $X$: $\mathbb{E}[X] = \int_{-\infty}^{\infty} x f(x) \, dx$

* Applying the PDF: $\mathbb{E}[X] = \int_0^{\infty} x \lambda e^{-\lambda x} \, dx$

* Integration by Parts: Use integration by parts where $u = x$ and $dv = \lambda e^{-\lambda x} dx$:  $\mathbb{E}[X] = \left[-\frac{x e^{-\lambda x}}{\lambda}\right]_0^\infty + \int_0^\infty \frac{1}{\lambda} e^{-\lambda x} \, dx = \frac{1}{\lambda}$

 **2.5 Variance**

The variance $\text{Var}(X)$ of the exponential distribution is given by: $\text{Var}(X) = \frac{1}{\lambda^2}$

Derivation of the Variance:

* Variance Formula: The variance is given by: $\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$

* Calculate $\mathbb{E}[X^2]$: $\mathbb{E}[X^2] = \int_0^{\infty} x^2 \lambda e^{-\lambda x} \, dx$

3. Integration by Parts: Apply integration by parts twice, or use the fact that: $\mathbb{E}[X^2] = \frac{2}{\lambda^2}$

4. Variance: $\text{Var}(X) = \frac{2}{\lambda^2} - \left(\frac{1}{\lambda}\right)^2 = \frac{1}{\lambda^2}$

**2.6 Memorylessness Property**

**Mathematically:** $P(X > s + t \mid X > t) = P(X > s)$
Where $X$ is a random variable representing the time until the next event, $s$ and $t$ are time intervals.

**Explanation:**

This property implies that the exponential distribution "forgets" how much time has already passed. For example, if a light bulb's lifetime follows an exponential distribution, the probability that it lasts another hour is the same regardless of how long it has already been on.

**2.7 Relationship between Exponential and Poisson Distributions**

The exponential distribution is closely related to the Poisson distribution.

Setup:
- Let $T_1, T_2, \dots$ be independent and identically distributed (i.i.d.) random variables following $EXP(\lambda)$.
- Define $S_k = T_1 + T_2 + \dots + T_k$ as the sum of the first $k$ exponential random variables.
- Let $X_i$ be the number of $S_k$ values that fall in the interval $[t_{i-1}, t_i]$, for $i = 1, 2, \dots, n$.

Key Result:
- $X_i$ follows a Poisson distribution: $X_i \sim P(\lambda(t_i - t_{i-1}))$.
- This result indicates that the number of events occurring in a given interval $[t_{i-1}, t_i]$ is Poisson distributed if the times between events follow an exponential distribution.

Reverse Relationship:
- If the number of events $X_i$ in each interval $[t_{i-1}, t_i]$ is Poisson distributed, then the time between consecutive events follows an exponential distribution.

Interpretation:
- The Poisson distribution models the number of events in a fixed time interval, while the exponential distribution models the time between those events.

**2.8 Interpreting $\lambda$**

The parameter $\lambda$ in the exponential and Poisson distributions has an important interpretation.

Exponential Distribution $EXP(\lambda)$:

- $\lambda$ represents the **rate** of events per time unit.
- **Mean Time Between Events:** The mean or expected time between events is given by $\frac{1}{\lambda}$. This means that, on average, events happen every $\frac{1}{\lambda}$ units of time.

Poisson Distribution $P(\lambda t)$:
- In the Poisson distribution, $\lambda t$ represents the expected number of events in a time interval of length $t$.
- **Mean Number of Events:** For a time interval of length $t$, the average number of events occurring is $\lambda t$.

Intuitive Example:
- If $\lambda = 5$ events per hour, then on average, 5 events are expected to occur every hour.
- The time between events, on average, is $\frac{1}{\lambda} = \frac{1}{5}$ hours, or 12 minutes.

---

#### **3. Gamma Distribution $ \text{Gamma}(\alpha, \lambda) $**

**3.1 Probability Density Function (PDF)**

The PDF of the gamma distribution $ \text{Gamma}(\alpha, \lambda) $ is given by: $f(x) = \begin{cases} 
\frac{\lambda^\alpha}{\Gamma(\alpha)} x^{\alpha - 1} e^{-\lambda x}, & \text{if } x \geq 0 \\
0, & \text{if } x < 0
\end{cases}$

- $ \alpha > 0 $ is the **shape parameter**.
- $ \lambda > 0 $ is the **rate (or scale) parameter**.
- $ \Gamma(\alpha) $ is the gamma function.

**Gamma Function $ \Gamma(\alpha) $:**

The gamma function $ \Gamma(\alpha) $ is defined as: $\Gamma(\alpha) = \int_0^\infty y^{\alpha-1} e^{-y} \, dy$

- For a positive integer $ \alpha = n $, $ \Gamma(n) = (n-1)! $.
- For $ \alpha = \frac{1}{2} $, $ \Gamma\left(\frac{1}{2}\right) = \sqrt{\pi} $.

Derivation of the PDF:

* Generalization of Exponential Distribution: The gamma distribution generalizes the exponential distribution, which is a special case when $ \alpha = 1 $.

* Shape and Scale: The parameter $ \alpha $ controls the shape, and $ \lambda $ scales the distribution. The PDF decreases exponentially with $ x $ but is modified by the $ x^{\alpha - 1} $ term, which can increase the probability for small values of $ x $ when $ \alpha $ is small.

**3.2 Cumulative Distribution Function (CDF)**

The CDF of the gamma distribution does not have a simple closed form like the exponential distribution. However, it can be expressed in terms of the incomplete gamma function: $F(x) = \frac{\gamma(\alpha, \lambda x)}{\Gamma(\alpha)}$

Where $ \gamma(\alpha, \lambda x) $ is the lower incomplete gamma function defined by: $\gamma(\alpha, \lambda x) = \int_0^{\lambda x} y^{\alpha-1} e^{-y} \, dy$

**3.3 Moment Generating Function (MGF)**

The MGF $ M_X(t) $ of the gamma distribution is given by: $M_X(t) = \left(\frac{\lambda}{\lambda - t}\right)^\alpha, \quad t < \lambda$

Derivation of the MGF:

* Definition: The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} f(x) \, dx$

* Substitute the PDF: $M_X(t) = \int_0^\infty e^{tx} \frac{\lambda^\alpha}{\Gamma(\alpha)} x^{\alpha - 1} e^{-\lambda x} \, dx = \frac{\lambda^\alpha}{\Gamma(\alpha)} \int_0^\infty x^{\alpha - 1} e^{-(\lambda - t)x} \, dx$

* Recognize the Gamma Function Form: $M_X(t) = \frac{\lambda^\alpha}{(\lambda - t)^\alpha} \cdot \frac{\Gamma(\alpha)}{\Gamma(\alpha)} = \left(\frac{\lambda}{\lambda - t}\right)^\alpha$

**3.4 Mean**

The mean $ \mathbb{E}[X] $ of the gamma distribution is given by: $\mathbb{E}[X] = \frac{\alpha}{\lambda}$

Derivation of the Mean:

* Definition: The mean is the expected value of $ X $: $\mathbb{E}[X] = \int_0^\infty x \cdot f(x) \, dx$

* Using the PDF: $\mathbb{E}[X] = \int_0^\infty x \cdot \frac{\lambda^\alpha}{\Gamma(\alpha)} x^{\alpha - 1} e^{-\lambda x} \, dx = \frac{\lambda^\alpha}{\Gamma(\alpha)} \int_0^\infty x^\alpha e^{-\lambda x} \, dx$

*  The integral now represents $ \Gamma(\alpha + 1) = \alpha \cdot \Gamma(\alpha) $, leading to: $\mathbb{E}[X] = \frac{\alpha}{\lambda}$

**3.5 Variance**

The variance $ \text{Var}(X) $ of the gamma distribution is given by: $\text{Var}(X) = \frac{\alpha}{\lambda^2}$

Derivation of the Variance:

* Variance Formula: The variance is calculated as: $\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$

* Calculate $ \mathbb{E}[X^2] $: Similar to the mean calculation, $ \mathbb{E}[X^2] $ involves computing: $\mathbb{E}[X^2] = \frac{\Gamma(\alpha + 2)}{\lambda^2 \Gamma(\alpha)} = \frac{\alpha(\alpha + 1)}{\lambda^2}$

* Variance: $\text{Var}(X) = \frac{\alpha(\alpha + 1)}{\lambda^2} - \left(\frac{\alpha}{\lambda}\right)^2 = \frac{\alpha}{\lambda^2}$

**3.6 Parameters:**

- $ \alpha > 0 $: Shape parameter
- $ \lambda > 0 $: Rate (or scale) parameter

**3.7 Example:** 

Used to model the default rate of credit portfolios in risk management. The gamma distribution is highly flexible and can model a variety of shapes by adjusting the parameters $ \alpha $ and $ \lambda $. This makes it useful in many applications, especially in fields like finance and risk management.

---

#### **4. Normal Distribution $N(\mu, \sigma^2)$**

The normal distribution is one of the most important distributions in probability and statistics, often used to model real-world phenomena due to the Central Limit Theorem.

**4.1 Probability Density Function (PDF)**

The PDF of the normal distribution $N(\mu, \sigma^2)$ is given by: $f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}, \quad x \in \mathbb{R}$

- $\mu$ is the **mean** or **expected value**.
- $\sigma^2$ is the **variance** of the distribution.
- $\sigma$ is the **standard deviation**.

Derivation of the PDF:

* Normalization: The normal distribution's PDF must integrate to 1 over the entire real line: $\int_{-\infty}^{\infty} f(x) \, dx = 1$

* Bell Shape: The function $f(x)$ is symmetric around the mean $\mu$, and the exponent $-\frac{(x - \mu)^2}{2\sigma^2}$ determines how quickly the probability density decreases as $x$ moves away from $\mu$.

**4.2 Cumulative Distribution Function (CDF)**

The CDF $F(x)$ of the normal distribution does not have a closed-form expression. However, it is defined as: $F(x) = P(X \leq x) = \int_{-\infty}^x f(u) \, du$

**Properties of the CDF:**

* **Standard Normal CDF:** For $Z \sim N(0, 1)$, the standard normal distribution, the CDF is denoted by $\Phi(z)$.

* **Transformation:** For $X \sim N(\mu, \sigma^2)$, the CDF can be related to the standard normal CDF by transforming $X$ to the standard normal form: $F(x) = \Phi\left(\frac{x - \mu}{\sigma}\right)$

**4.3 Moment Generating Function (MGF)**

The MGF $M_X(t)$ of the normal distribution is given by: $M_X(t) = e^{\mu t + \frac{\sigma^2 t^2}{2}}, \quad t \in \mathbb{R}$

Derivation of the MGF:

* Definition: The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} f(x) \, dx$

* Substituting the PDF: $M_X(t) = \frac{1}{\sigma \sqrt{2\pi}} \int_{-\infty}^{\infty} e^{tx} e^{-\frac{(x - \mu)^2}{2\sigma^2}} \, dx$

* Completing the Square: Combine the exponentials and complete the square: $M_X(t) = e^{\mu t + \frac{\sigma^2 t^2}{2}}$

**4.4 Mean**

The mean $\mathbb{E}[X]$ of the normal distribution is simply: $\mathbb{E}[X] = \mu$

Derivation of the Mean:

* Symmetry: The normal distribution is symmetric around $\mu$, so $\mu$ is the center of the distribution.
* Integration: Direct integration of $x \cdot f(x)$ over all $x$ confirms that the mean is $\mu$.

**4.5 Variance**

The variance $\text{Var}(X)$ of the normal distribution is: $\text{Var}(X) = \sigma^2$

Derivation of the Variance:

* Variance Formula: The variance is calculated as: $\text{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$

* Calculate $\mathbb{E}[X^2]$: For a normal distribution, the second moment $\mathbb{E}[X^2]$ is given by: $\mathbb{E}[X^2] = \sigma^2 + \mu^2$

* Variance: Subtracting the square of the mean $\mu^2$, we get: $\text{Var}(X) = \sigma^2$

**4.6 Important Notes**

* **Bell-Shaped PDF:** The normal distribution is bell-shaped and symmetric around $\mu$.

* **Linear Transformation:** If $X \sim N(\mu, \sigma^2)$ and $Y = aX + b$, then $Y \sim N(a\mu + b, a^2\sigma^2)$.

* **Central Limit Theorem (CLT):** The normal distribution plays a central role in probability and statistics due to the CLT, which states that the sum (or average) of a large number of independent, identically distributed random variables tends to follow a normal distribution, regardless of the original distribution.

* **Standard Normal Distribution:** The standard normal distribution $Z \sim N(0, 1)$ is a special case where $\mu = 0$ and $\sigma^2 = 1$​.

---

**5. Chi-Square Distribution $ \chi^2_n $**

The chi-square distribution is widely used in statistics, particularly in hypothesis testing and confidence interval estimation for variance. It is a special case of the gamma distribution and arises as the distribution of the sum of squared standard normal variables.

**5.1 Probability Density Function (PDF)**

The PDF of the chi-square distribution with $ n $ degrees of freedom is given by: $f(x) = \begin{cases} \frac{1}{2^{n/2}\Gamma(n/2)} x^{\frac{n}{2}-1} e^{-x/2}, & \text{if } x \geq 0 \\ 0, & \text{if } x < 0 \end{cases}$

- $ n $ is the **degrees of freedom**.
- $ \Gamma(\cdot) $ is the gamma function.

Derivation of the PDF:

Special Case of Gamma Distribution: The chi-square distribution is a special case of the gamma distribution where $ \alpha = \frac{n}{2} $ and $ \lambda = \frac{1}{2} $. The gamma distribution's PDF is: $f(x) = \frac{\lambda^\alpha}{\Gamma(\alpha)} x^{\alpha - 1} e^{-\lambda x}$

Substituting $ \alpha = \frac{n}{2} $ and $ \lambda = \frac{1}{2} $ gives: $f(x) = \frac{1}{2^{n/2}\Gamma(n/2)} x^{\frac{n}{2}-1} e^{-x/2}$ 

**5.2 Cumulative Distribution Function (CDF)**

The CDF of the chi-square distribution is not expressed in a simple closed form. However, it can be represented using the lower incomplete gamma function $ \gamma(\alpha, x) $: $F(x) = \frac{\gamma(n/2, x/2)}{\Gamma(n/2)}$

Where $ \gamma(\alpha, x) $ is the lower incomplete gamma function: $\gamma(\alpha, x) = \int_0^x t^{\alpha - 1} e^{-t} \, dt$

**5.3 Moment Generating Function (MGF)**

The MGF $ M_X(t) $ of the chi-square distribution is given by: $M_X(t) = \left(\frac{1}{1 - 2t}\right)^{n/2}, \quad t < \frac{1}{2}$

Derivation of the MGF:

* Definition: The MGF is defined as: $M_X(t) = \mathbb{E}[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} f(x) \, dx$

* Substitute the PDF: $M_X(t) = \int_0^\infty e^{tx} \frac{1}{2^{n/2}\Gamma(n/2)} x^{\frac{n}{2}-1} e^{-x/2} \, dx$

* Combining the Exponentials: $M_X(t) = \frac{1}{2^{n/2}\Gamma(n/2)} \int_0^\infty x^{\frac{n/2}-1} e^{-x(1/2 - t)} \, dx$

Recognizing the integral as the gamma function gives: $M_X(t) = \left(\frac{1}{1 - 2t}\right)^{n/2}$

**5.4 Mean**

The mean $ \mathbb{E}[X] $ of the chi-square distribution is given by: $\mathbb{E}[X] = n$

Derivation of the Mean:

Sum of Squared Normals: The chi-square distribution with $ n $ degrees of freedom is the sum of $ n $ independent standard normal random variables squared. Since each $ Z_i^2 $ has an expected value of 1: $\mathbb{E}[X] = \mathbb{E}\left[\sum_{i=1}^n Z_i^2\right] = \sum_{i=1}^n \mathbb{E}[Z_i^2] = n$

**5.5 Variance**

The variance $ \text{Var}(X) $ of the chi-square distribution is given by: $\text{Var}(X) = 2n$

Derivation of the Variance:

Variance of Sum of Independent Variables: The variance of the sum of independent random variables is the sum of their variances. Since each $ Z_i^2 $ has a variance of 2: $\text{Var}(X) = \text{Var}\left(\sum_{i=1}^n Z_i^2\right) = \sum_{i=1}^n \text{Var}(Z_i^2) = 2n$

**5.6 Important Notes**

* **Special Case of Gamma Distribution:** The chi-square distribution is a special case of the gamma distribution with parameters $ \alpha = \frac{n}{2} $ and $ \lambda = \frac{1}{2} $.

* **Sum of Independent Chi-square Variables:** If $ X_1, \dots, X_k $ are independent and $ X_i \sim \chi^2_{n_i} $, then $ Y = X_1 + \dots + X_k \sim \chi^2_{n_1 + \dots + n_k} $.

* **Relationship with Standard Normal:** If $ Z \sim N(0, 1) $, then $ Z^2 \sim \chi^2_1 $.

**5.7 Detailed Proof of the Two Properties**

<u>1. Sum of Independent Chi-Square Variables</u>**

**Statement:** If $ X_1, \dots, X_k $ are independent and $ X_i \sim \chi^2_{n_i} $, then the sum $ Y = X_1 + \dots + X_k $ follows a chi-square distribution with degrees of freedom $ n_1 + \dots + n_k $, i.e., $ Y = X_1 + \dots + X_k \sim \chi^2_{n_1 + \dots + n_k} $.

Proof:

1. Moment Generating Function (MGF) of a Chi-Square Distribution:

   The MGF of a chi-square random variable $ X_i \sim \chi^2_{n_i} $ is given by: $ M_{X_i}(t) = \left(1 - 2t\right)^{-\frac{n_i}{2}}, \quad \text{for } t < \frac{1}{2} $.

2. MGF of the Sum of Independent Variables:

   Since the $ X_i $ are independent, the MGF of the sum $ Y $ is the product of their MGFs: $ M_Y(t) = M_{X_1}(t) \cdot M_{X_2}(t) \cdot \dots \cdot M_{X_k}(t) $.

   Substituting the MGFs of the chi-square distributions: $ M_Y(t) = \left(1 - 2t\right)^{-\frac{n_1}{2}} \cdot \left(1 - 2t\right)^{-\frac{n_2}{2}} \cdot \dots \cdot \left(1 - 2t\right)^{-\frac{n_k}{2}} $.

3. Simplifying the Expression: Combine the exponents: $ M_Y(t) = \left(1 - 2t\right)^{-\frac{n_1 + n_2 + \dots + n_k}{2}} $.

4. Conclusion: The MGF of $ Y $ is identical to the MGF of a chi-square distribution with degrees of freedom $ n_1 + n_2 + \dots + n_k $. Hence, $ Y $ follows a chi-square distribution with these degrees of freedom: $ Y \sim \chi^2_{n_1 + n_2 + \dots + n_k} $.


<u>2. Relationship with Standard Normal</u>

**Statement:** If $ Z \sim N(0, 1) $, then $ Z^2 \sim \chi^2_1 $.

Proof:

1. PDF of Standard Normal Distribution: The probability density function (PDF) of the standard normal distribution $ Z \sim N(0, 1) $ is: $ f_Z(z) = \frac{1}{\sqrt{2\pi}} e^{-\frac{z^2}{2}}, \quad z \in \mathbb{R} $.

2. Transforming to a Chi-Square Distribution: Consider the transformation $ Y = Z^2 $. The distribution of $ Y $ can be derived using the change of variables technique.

3. Change of Variables: Let $ y = z^2 $, so that $ z = \pm\sqrt{y} $. The Jacobian determinant for the transformation is $ \frac{1}{2\sqrt{y}} $.

   The PDF of $ Y = Z^2 $ is then: $ f_Y(y) = \frac{1}{\sqrt{2\pi}} \left( \frac{e^{-\frac{y}{2}}}{\sqrt{y}} + \frac{e^{-\frac{y}{2}}}{\sqrt{y}} \right) = \frac{1}{\sqrt{2\pi y}} e^{-\frac{y}{2}}, \quad y \geq 0 $.

   Simplifying: $ f_Y(y) = \frac{1}{2^{\frac{1}{2}} \Gamma\left(\frac{1}{2}\right)} y^{\frac{1}{2} - 1} e^{-\frac{y}{2}}, \quad y \geq 0 $.

4. Identifying the Chi-Square Distribution: The PDF derived above matches the PDF of the chi-square distribution with 1 degree of freedom $ \chi^2_1 $: $ f_Y(y) = \frac{1}{\Gamma\left(\frac{1}{2}\right) 2^{\frac{1}{2}}} y^{\frac{1}{2} - 1} e^{-\frac{y}{2}}, \quad y \geq 0 $. Therefore: $ Y = Z^2 \sim \chi^2_1 $.


---

#### 6. F-Distribution $ F_{m,n} $

The F-distribution arises frequently in the context of analysis of variance (ANOVA) and is used to compare variances. It is the distribution of the ratio of two scaled chi-square distributions.

**6.1 Probability Density Function (PDF)**

The PDF of the F-distribution with $ m $ and $ n $ degrees of freedom is complex and given by: $f(x) = \frac{\sqrt{\frac{(mn)^m}{(m+n)^{m+n}}} \cdot \left(\frac{x}{m}\right)^{m/2-1} \cdot \left(1+\frac{mx}{n}\right)^{-(m+n)/2}}{B\left(\frac{m}{2}, \frac{n}{2}\right)}$

- $ m $ and $ n $ are the **degrees of freedom**.
- $ B\left(\frac{m}{2}, \frac{n}{2}\right) $ is the Beta function, defined as: $B(a, b) = \int_0^1 t^{a-1} (1-t)^{b-1} \, dt = \frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}$

Derivation of the PDF:

* Ratio of Chi-square Distributions: The F-distribution is defined as the ratio of two independent chi-square distributed variables, scaled by their respective degrees of freedom. Specifically, if $ U \sim \chi^2_m $ and $ V \sim \chi^2_n $ are independent, then: $F = \frac{(U/m)}{(V/n)} \sim F_{m,n}$

* Using the Relationship with the Beta Distribution: The F-distribution can be derived from the Beta distribution since if $ X \sim \text{Beta}(a,b) $, then $ \frac{bX}{a(1-X)} \sim F_{2a, 2b} $.

**6.2 Cumulative Distribution Function (CDF)**

The CDF of the F-distribution does not have a simple closed-form expression but can be computed using the incomplete beta function $ I_x(a, b) $, related to the regularized incomplete beta function $ B_x(a, b) $: $F(x) = I_{\frac{mx}{mx+n}} \left(\frac{m}{2}, \frac{n}{2}\right)$

- $ I_x(a, b) $ is the regularized incomplete beta function.

**6.3 Moment Generating Function (MGF)**

The MGF of the F-distribution does not have a closed-form expression, largely due to the complex nature of the distribution. Instead, its characteristic function or the first few moments (mean, variance) are often used to understand its properties.

**6.4 Mean**

The mean $ \mathbb{E}[X] $ of the F-distribution is: $\mathbb{E}[X] = \frac{n}{n-2} \quad \text{for } n > 2$

Derivation of the Mean:

* Expectation Formula: The mean of the F-distribution is derived using properties of the chi-square and beta distributions, but it requires that the second degree of freedom $ n $ be greater than 2 for the expectation to exist.

**6.5 Variance**

The variance $ \text{Var}(X) $ of the F-distribution is given by: $\text{Var}(X) = \frac{2n^2(m+n-2)}{m(n-2)^2(n-4)} \quad \text{for } n > 4$

Derivation of the Variance:

* Variance Formula: The variance of the F-distribution involves higher moments and can be quite complex. The existence of the variance requires that $ n > 4 $.

**6.6 Important Notes**

1. **Relationship with Chi-square Distribution:**
   - If $ U \sim \chi^2_m $ and $ V \sim \chi^2_n $ are independent, then $ \frac{U/m}{V/n} \sim F_{m,n} $.
   
2. **Relationship with t-Distribution:**
   - If $ X \sim t_n $, then $ X^2 \sim F_{1,n} $.

3. **Inverse F-Distribution:**
   - If $ X \sim F_{m,n} $, then $ X^{-1} \sim F_{n,m} $.

**6.7 Detailed Proof of the Three Notes** 

<u>Note 1: Relationship between Chi-Square Distributions and the F-Distribution</u>

**Statement:** Let $ U \sim \chi^2_m $ and $ V \sim \chi^2_n $ be independent. Then the ratio $ \frac{U/m}{V/n} $ follows an F-distribution with $ m $ and $ n $ degrees of freedom, denoted as $ F_{m,n} $.

Proof:

1. Chi-Square Distribution: 
   - $ U \sim \chi^2_m $ implies $ U $ is the sum of squares of $ m $ independent standard normal variables.
   - $ V \sim \chi^2_n $ implies $ V $ is the sum of squares of $ n $ independent standard normal variables.
  
2. Define the Ratio:
   - The random variable $ F = \frac{U/m}{V/n} $ is defined.
   - Simplify this to $ F = \frac{U \cdot n}{V \cdot m} $.

3. Distribution of the Ratio:
   - The distribution of $ F $ can be derived by finding the joint distribution of $ U $ and $ V $ and using the transformation method.
   - The result is that $ F \sim F_{m,n} $, meaning $ F $ follows an F-distribution with $ m $ and $ n $ degrees of freedom.

<u>Note 2: Relationship between the t-Distribution and the F-Distribution</u>

**Statement:** Let $ X \sim t_n $, then $ Y = X^2 $ follows an F-distribution with 1 and $ n $ degrees of freedom, denoted as $ F_{1,n} $.

Proof:

1. t-Distribution:
   - $ X \sim t_n $ implies $ X = \frac{Z}{\sqrt{V/n}} $, where $ Z \sim N(0,1) $ and $ V \sim \chi^2_n $ are independent.

2. Square the t-Variable:
   - Square $ X $ to obtain $ Y = X^2 = \frac{Z^2}{V/n} $.

3. Recognize the Distribution:
   - $ Z^2 \sim \chi^2_1 $, and hence $ Y = \frac{Z^2/n}{V/n} = \frac{Z^2}{V/n} $.
   - Therefore, $ Y \sim F_{1,n} $.

<u>Note 3: Reciprocal of F-distribution</u>

**Statement:** If $ X \sim F_{m,n} $, then the reciprocal $ X^{-1} $ follows an F-distribution with degrees of freedom swapped, i.e., $ X^{-1} \sim F_{n,m} $.

Proof:

1. Consider $ X \sim F_{m,n} $:
   - $ X = \frac{U/m}{V/n} $ where $ U \sim \chi^2_m $ and $ V \sim \chi^2_n $, and both are independent.
   
2. Reciprocal of $ X $:
   - Take the reciprocal $ X^{-1} = \frac{V/n}{U/m} = \frac{V \cdot m}{U \cdot n} $.

3. Recognize the Distribution:
   - The new random variable $ X^{-1} $ has the same form as an F-distribution but with degrees of freedom swapped, so $ X^{-1} \sim F_{n,m} $.

---

#### 7. Mean and Variance of Normal Random Sample

Let's break down the problem step by step to thoroughly understand the concepts and the reasoning behind the degrees of freedom $n-1$ instead of $n$. This will involve some important concepts in statistics, particularly when dealing with normal random samples.

**7.1 Sample Mean and Sample Variance**

Given a random sample $X_1, X_2, \dots, X_n$ from a normal distribution $N(\mu, \sigma^2)$, the sample mean $\bar{X}_n$ and sample variance $S_n^2$ are defined as: 

* **Sample Mean:** $ \bar{X}_n = \frac{1}{n} \sum_{i=1}^{n} X_i $​

- **Sample Variance:** $ S_n^2 = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \bar{X}_n)^2 $

**7.2** **Distribution of the Sample Mean $ \bar{X}_n $**

The sample mean $ \bar{X}_n $ follows a normal distribution: $ \bar{X}_n \sim N\left(\mu, \frac{\sigma^2}{n}\right) $

This result comes from the fact that the sum of independent normal random variables is also normally distributed. The mean of the sample mean is $ \mu $, and the variance of the sample mean is $ \frac{\sigma^2}{n} $.

**7.3** **Independence of $ \bar{X}_n $ and $ S_n^2 $**

The sample mean $ \bar{X}_n $ and the sample variance $ S_n^2 $ are independent. This independence is a critical property that comes from the fact that the distribution of $ S_n^2 $ depends only on the deviations $ X_i - \bar{X}_n $, which are independent of the sample mean.

**7.4** **Distribution of the Sample Variance $ S_n^2 $**

The sample variance $ S_n^2 $ is related to the chi-square distribution. Specifically: $ (n-1) \frac{S_n^2}{\sigma^2} \sim \chi^2_{n-1} $

This result indicates that the scaled sample variance follows a chi-square distribution with $ n-1 $ degrees of freedom.

**7.5** **Distribution of $ \sqrt{n} \frac{(\bar{X}_n - \mu)}{\sigma} $**

The term $ \sqrt{n} \frac{(\bar{X}_n - \mu)}{\sigma} $ follows a standard normal distribution: $ \sqrt{n} \frac{(\bar{X}_n - \mu)}{\sigma} \sim N(0, 1) $

**7.6 t-Distribution and Its Relation**

The ratio $ \frac{\sqrt{n} (\bar{X}_n - \mu)}{S_n} $ follows a t-distribution with $ n-1 $ degrees of freedom: $ \frac{\sqrt{n} (\bar{X}_n - \mu)}{S_n} \sim t_{n-1} $

This result is due to the relationship between the normal distribution, chi-square distribution, and the t-distribution.

**7.7 Why the Degrees of Freedom is $ n-1 $ Instead of $ n $**

The degrees of freedom in the sample variance calculation are reduced by 1 because the sample mean $ \bar{X}_n $ is itself an estimate and is used in calculating the variance. Each sample point $ X_i $ contributes one piece of information, but since $ \bar{X}_n $ is calculated from all $ X_i $, the degrees of freedom are reduced by 1 to account for the estimation of $ \mu $ by $ \bar{X}_n $.

In other words, there is a constraint on the data, as the sum of the deviations from the mean must be zero: $ \sum_{i=1}^n (X_i - \bar{X}_n) = 0 $.  This constraint reduces the effective number of independent pieces of information from $ n $ to $ n-1 $.

**7.8 Are $ (X_1 - \bar{X}_n, \dots, X_n - \bar{X}_n) $ Independent?**

No, the terms $ (X_1 - \bar{X}_n, \dots, X_n - \bar{X}_n) $ are not independent. This is because they are constrained by the condition: $ \sum_{i=1}^n (X_i - \bar{X}_n) = 0 $     This constraint creates a dependency among the terms. For example, if you know $ n-1 $ of these differences, the last one is automatically determined.

---

### **III. Types of Convergence**

---

#### 1. **Convergence Concepts with the Coin Toss Example**

**Question 1: Toss a fair coin 2 or 3 times. Can you accurately predict the average appearance of heads?**

When you toss a fair coin only a few times (like 2 or 3 times), the outcome is highly variable. For example:

- You might get heads twice, giving you an average of $ \frac{2}{2} = 1 $.
- Or you might get heads once and tails once, giving you an average of $ \frac{1}{2} = 0.5 $.

Since there are so few trials, your estimate of the average appearance of heads is not likely to be accurate.

**Question 2: Toss a fair coin many times. What will you predict the average appearance of heads?**

As you toss the coin more and more times, the Law of Large Numbers tells us that the average number of heads will converge to the true probability of getting a head in a single toss, which is 0.5 for a fair coin.

- If you toss the coin 1000 times, and it's fair, the average number of heads should be close to 0.5.
- If you toss it 10,000 times, this average will be even closer to 0.5.

---

#### **2. Types of Convergence**

**2.1 Almost Sure Convergence**

**Definition:** A sequence of random variables $ \{Z_n\} $ converges **almost surely** to a random variable $ Z $ if, for any $ \epsilon > 0 $,

$ P\left(\lim_{n \to \infty} |Z_n - Z| < \epsilon \right) = 1 $

This means that as $ n $ approaches infinity, the probability that $ Z_n $ is within any small distance $ \epsilon $ of $ Z $ becomes 1. In other words, $ Z_n $ will get closer and closer to $ Z $ for almost every outcome.

**Example:** Consider our coin toss example. Let $ Z_n $ represent the proportion of heads after $ n $ tosses. The sequence $ \{Z_n\} $ converges **almost surely** to 0.5 as $ n $ increases.

**2. Convergence in Probability**

- **Definition:** A sequence of random variables $ \{Z_n\} $ converges **in probability** to a random variable $ Z $ if, for any $ \epsilon > 0 $,

$ \lim_{n \to \infty} P\left(|Z_n - Z| < \epsilon\right) = 1 $

This means that as $ n $ increases, the probability that $ Z_n $ is within $ \epsilon $ of $ Z $ approaches 1. However, this does not guarantee that $ Z_n $ will always get closer to $ Z $ in every sequence (unlike almost sure convergence).

**Example:** Again, using the coin toss, the proportion of heads $ Z_n $ converges **in probability** to 0.5. As you toss the coin more times, the probability that the proportion of heads is close to 0.5 gets closer to 1.

**Relationship Between Convergence Concepts**

- **Almost sure convergence** implies **convergence in probability**. If a sequence of random variables converges almost surely to a limit, then it also converges in probability to that limit.
- **Convergence in probability** does not imply **almost sure convergence**. A sequence might converge in probability without almost surely converging, as almost sure convergence is a stronger condition.

**几乎必然收敛** 的一个例子是抛硬币的实验：

假设你有一个硬币，每次抛硬币得到正面（1）或反面（0）的概率都是 $ \frac{1}{2} $。定义一个随机变量 $ X_n $ 表示前 $ n $ 次抛硬币中出现正面的比例。显然，随着 $ n $ 的增大，$ X_n $ 会趋向于 $ \frac{1}{2} $，也就是说，$ X_n $ 几乎必然收敛于 $ \frac{1}{2} $。因为当 $ n $ 无限增大时，抛硬币的频率法则（大数定律）告诉我们，得到正面的比例必然趋于 $ \frac{1}{2} $。

然而，如果我们考虑一个序列 $ Y_n $，它是这样定义的：当 $ n $ 是偶数时 $ Y_n = 0 $，当 $ n $ 是奇数时 $ Y_n = 1 $。这个序列依概率收敛于 $ \frac{1}{2} $，但不几乎必然收敛。因为虽然在大多数情况下，$ Y_n $ 的值是 $ 0 $ 或 $ 1 $，但它不会在任意一个单一值上集中。所以它并不满足几乎必然收敛的条件，但它在概率上可以看作是“均值”趋于 $ \frac{1}{2} $。

- **几乎必然收敛**是指序列在几乎所有样本路径上都趋向于一个固定值。
- **依概率收敛**是指序列在概率上越来越接近一个固定值，但并不要求在所有样本路径上都收敛到同一个值。

**Understanding $ n \to \infty $ in the Context of Large Data**

In statistical contexts, $ n \to \infty $ often represents a situation where the sample size becomes very large. As $ n $ increases, the observed averages and other statistics derived from the data are expected to converge to their true underlying values due to the Law of Large Numbers and the Central Limit Theorem.

---

#### **3. Convergence in Distribution**

Convergence in distribution (also known as weak convergence) is concerned with the convergence of the cumulative distribution functions (CDFs) of a sequence of random variables.

- **Definition:** A sequence of random variables $ \{Z_n\} $ converges in distribution to a random variable $ Z $, denoted by $ Z_n \xrightarrow{d} Z $, if the CDFs $ F_n(z) $ of $ Z_n $ converge to the CDF $ F(z) $ of $ Z $ at every point $ z $ where $ F(z) $ is continuous. $ \lim_{n \to \infty} F_n(z) = F(z) $

This means that as $ n $ increases, the distribution of $ Z_n $ becomes closer to the distribution of $ Z $.

---

#### **4. Properties of the Three Types of Convergence**

The following properties explain the relationships between almost sure convergence, convergence in probability, and convergence in distribution:

1. **Almost sure convergence implies convergence in probability, which in turn implies convergence in distribution**:
   - If $ Z_n \xrightarrow{\text{a.s.}} Z $, then $ Z_n \xrightarrow{P} Z $.
   - If $ Z_n \xrightarrow{P} Z $, then $ Z_n \xrightarrow{d} Z $.

   **Reasoning:** Almost sure convergence is the strongest form, ensuring that the sequence converges almost everywhere. This naturally implies convergence in probability, which in turn implies convergence in distribution, as distributional convergence is a weaker condition.

2. **Convergence in probability implies convergence in distribution**:
   - If $ Z_n \xrightarrow{P} Z $, then $ Z_n \xrightarrow{d} Z $.

   **Reasoning:** Since convergence in probability ensures that for any small positive $ \epsilon $, the probability that $ |Z_n - Z| $ is smaller than $ \epsilon $ approaches 1 as $ n $ increases, this leads to convergence in the distributional sense.

3. **Convergence to a constant**:
   - If $ Z_n \xrightarrow{d} c $, where $ c $ is a constant, then $ Z_n \xrightarrow{P} c $ and $ Z_n \xrightarrow{\text{a.s.}} c $.

   **Reasoning:** Convergence in distribution to a constant implies that the random variables $ Z_n $ are becoming increasingly concentrated around the constant value $ c $. This ensures that they will converge in probability and almost surely to $ c $.

4. **Convergence preserved by continuous transformations**:
   - If $ Z_n \xrightarrow{d} Z $ and $ g $ is a continuous function, then $ g(Z_n) \xrightarrow{d} g(Z) $.

   **Reasoning:** A continuous transformation of a convergent sequence of random variables preserves the convergence in distribution. The continuous mapping theorem formalizes this concept.

---

#### **5. Slutsky’s Theorem**

Slutsky's Theorem is a powerful result that relates products, sums, and ratios of converging sequences of random variables.

**Theorem:** If $ X_n \xrightarrow{d} X $ and $ Y_n \xrightarrow{P} a $ where $ a $ is a constant, then:

- (a) $ Y_n X_n \xrightarrow{d} aX $
- (b) $ Y_n + X_n \xrightarrow{d} X + a $
- (c) $ \frac{X_n}{Y_n} \xrightarrow{d} \frac{X}{a} $, provided $ P(Y_n \neq 0) = 1 $ and $ a \neq 0 $.

**Reasoning:** Slutsky's Theorem combines converging sequences in different manners, demonstrating that convergence in distribution is preserved under certain algebraic operations, provided one of the sequences converges in probability.

---

#### **6. Limit Theorem for the Delta Method**

The Delta Method is used to approximate the distribution of a function of a random variable that is asymptotically normal.

**Theorem:** Suppose $ \sqrt{n}(Y_n - \theta)/\sigma \xrightarrow{d} N(0,1) $. For a function $ g $ such that $ g'(\theta) \neq 0 $, $ \sqrt{n}\left[g(Y_n) - g(\theta)\right]/\sigma |g'(\theta)| \xrightarrow{d} N(0,1) $

 **Reasoning:** The Delta Method leverages the fact that if $ Y_n $ converges to $ \theta $ and is asymptotically normal, then $ g(Y_n) $ will also be asymptotically normal, with the scaling factor being determined by the derivative of $ g $ at $ \theta $.

---

### **IV. Law of Large Number**

---

#### **1. Law of Large Numbers (LLN)**
The **Law of Large Numbers** states that as the number of independent, identically distributed (i.i.d.) random variables $X_1, X_2, \dots, X_n$ increases, the sample average $\overline{X}_n$ (the average of the first $n$ observations) will converge in probability to the expected value $\mu = E(X_i)$. Mathematically, it can be expressed as: 

$ \overline{X}_n = \frac{1}{n}\sum_{i=1}^{n}X_i \xrightarrow{P} \mu $     where $\overline{X}_n$ is the sample mean, and $P$ indicates convergence in probability.

**Proof Outline:**

- We know $E(X_i) = \mu$ and $Var(X_i) = \sigma^2$.
- By the definition of the sample mean, $E(\overline{X}_n) = \mu$.
- By the Central Limit Theorem (CLT) and Chebyshev's inequality, we can show that the probability that $\overline{X}_n$ deviates from $\mu$ by more than any positive $\epsilon$ becomes arbitrarily small as $n$ increases. Thus, $\overline{X}_n$ converges to $\mu$ in probability.

---

#### **2. Monte Carlo Integration**
Monte Carlo integration is a method used to estimate the value of an integral using random sampling.

**Goal:**

To calculate the integral $ I(f) = \int_0^1 f(x) \, dx $ using a Monte Carlo method.

**Steps:**

1. **Generate Sample Points**: Generate $n$ i.i.d. random variables $X_1, X_2, \dots, X_n$ uniformly distributed on $[0, 1]$, i.e., $X_i \sim U(0, 1)$.
   
2. **Compute the Sample Mean**: Calculate the sample mean of the function values at these points:
   $ \hat{I}(f) = \frac{1}{n} \sum_{i=1}^{n} f(X_i) $
   This sample mean $\hat{I}(f)$ serves as the Monte Carlo estimate of the integral $I(f)$.

3. **Apply the Law of Large Numbers**: According to LLN, as $n$ becomes large, the sample mean $\hat{I}(f)$ will converge in probability to the expected value of $f(X)$, which is the value of the integral $I(f)$:
   $ \hat{I}(f) \xrightarrow{P} E[f(X)] = \int_0^1 f(x) \, dx = I(f) $

---

### **V. Central Limit Theorem**

The **Central Limit Theorem (CLT)** is a fundamental theorem in probability theory. It states that, given a sufficiently large number of independent and identically distributed (i.i.d.) random variables with a finite mean and variance, the distribution of the sum (or average) of these variables approaches a normal distribution as the number of variables increases.

---

#### 1. Mathematical Formulation
Let $ X_1, X_2, \dots, X_n $ be i.i.d. random variables with mean $ \mu $ and variance $ \sigma^2 $. Define: $ \overline{X}_n = \frac{1}{n} \sum_{i=1}^{n} X_i $
as the sample mean and $ T_n = n\overline{X}_n $ as the sum of these variables.

According to the CLT: $ \lim_{n \to \infty} P\left(\frac{T_n - n\mu}{\sigma\sqrt{n}} \leq x\right) = \lim_{n \to \infty} P\left(\frac{\sqrt{n}(\overline{X}_n - \mu)}{\sigma} \leq x\right) = \Phi(x) $, where $ \Phi(x) $ is the cumulative distribution function (CDF) of the standard normal distribution $ N(0,1) $.

This means that as $ n $ becomes large, the standardized sum $ \frac{T_n - n\mu}{\sigma\sqrt{n}} $ (or equivalently, the standardized mean $ \frac{\sqrt{n}(\overline{X}_n - \mu)}{\sigma} $) converges in distribution to $ N(0,1) $.

#### 2. Normal Approximation to Binomial Distribution

Let's consider the binomial distribution as an example of applying the CLT. 

Suppose $ X_1, X_2, \dots $ are i.i.d. Bernoulli random variables with parameter $ p $, i.e., $ X_i \sim B(1, p) $. The sum $ T_n = X_1 + X_2 + \dots + X_n $ is binomially distributed, $ T_n \sim B(n, p) $.

The mean and variance of each $ X_i $ are: $ E(X_i) = p, \quad Var(X_i) = p(1-p) $ Therefore, the sum $ T_n $ has: $ E(T_n) = np, \quad Var(T_n) = np(1-p) $

According to the CLT, when $ n $ is large enough, the standardized version of $ T_n $ can be approximated by a normal distribution: $ \frac{T_n - np}{\sqrt{np(1-p)}} \xrightarrow{d} N(0,1) $

This means that the binomial distribution $ B(n, p) $ can be approximated by a normal distribution $ N(np, np(1-p)) $ when $ n $ is large. This approximation is particularly useful because the normal distribution is easier to work with, especially when dealing with probabilities and percentiles.

#### 3. Sampling error

1. **Context**:
   - Suppose you're interested in knowing the average income $ \mu $ of families in Singapore.
   - If you could ask every family in Singapore for their income, you would get the true average income $ \mu $.

2. **Sampling**:
   - Instead of asking every family, you take a random sample of 1000 families and calculate the average income of these 1000 families. Let's denote this sample average by $ \overline{X}_{1000} $.

3. **Sampling Error**:
   - The difference between the sample average $ \overline{X}_{1000} $ and the true average $ \mu $ is called the sampling error, denoted by $ \overline{X}_{1000} - \mu $.
   - This error arises because the sample might not perfectly represent the entire population.

4. **Assessment of Sampling Error**:
   - The sampling error can be assessed by understanding its distribution. Under certain conditions (like the Central Limit Theorem), the sampling distribution of $ \overline{X}_{1000} $ is approximately normal with mean $ \mu $ and variance $ \frac{\sigma^2}{1000} $, where $ \sigma^2 $ is the population variance.
   - Therefore, the sampling error can be assessed using confidence intervals or hypothesis testing to determine how close $ \overline{X}_{1000} $ is likely to be to $ \mu $.

#### **4. Experimental error**

1. **Context**
   - Consider an experimental error $ \epsilon $, which is the sum of multiple small component errors: $ \epsilon = a_1\epsilon_1 + a_2\epsilon_2 + \dots + a_n\epsilon_n $.
   - These errors could arise from various sources, such as measurement inaccuracies, variations in raw materials, or differences in experimental conditions.

2. **Why Normal Distribution?**
   - According to the Central Limit Theorem (CLT), when these component errors are independent and identically distributed, the sum (or a linear combination) of these errors will tend to follow a normal distribution as the number of components becomes large.

3. **Implication**
   - Because of this property, the overall experimental error $ \epsilon $ can often be assumed to be normally distributed, even if the individual components are not normally distributed.
   - This assumption of normality simplifies statistical analysis and is foundational for many statistical methods, such as regression analysis and hypothesis testing.

