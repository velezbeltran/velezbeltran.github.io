---
title: "Exercise 2.3.3"
weight: 2
date: "2025-04-15"
math: true
draft: false
---
Let $S_1, S_2, \dots$ be independent exponential random variables with parameters $\lambda_1, \lambda_2, \dots$ respectively.
Then:
- Show that the distribution of $\lambda_1 S_1$ is exponential of parameter $1$.
- Use the strong law of large numbers to show, first in the special case for $\lambda_n = 1$ for all $n$, and then subject to $\sup_n \lambda_n < \infty$, that 
$$
\Pr\left( \sum_{n=1}^\infty \frac{S_n}{\lambda_n} = \infty \right) = 1
$$
Is the condition that $\sup_n \lambda_n < \infty$ necessary?

<!--
<details>
<summary><strong>Solution</strong></summary>
-->

# Solution

**Part 1**

This is evident from the the CDF as 
$$ 
\begin{aligned}
\Pr( \lambda_1 S_1 \leq s) = \Pr\left( S_1 \leq \frac{s}{\lambda_1}\right) = 1 - e^{-\lambda_1 \frac{s}{\lambda_1}} = 1 - e^{-s}
\end{aligned}
$$
This is the CDF of an exponential random variable with parameter $1$.

**Part 2**

First assume that $\lambda_n = 1$ for all $n$. Then, by the strong law of large  numbers and as $\E[S_n] =  1$ we know that w.p $1$ we have
$$ 
\lim_n \sum_{i=1}^n \frac{S_i}{n} = 1
$$
Or equivalently that the ratio of the series $\sum_{i=1}^n S_i$ and $n$ converges. 
Because $n$ diverges then this must mean that $\sum_{i=1}^n S_i$ diverges as well.
This is sufficient for the case where $\lambda_n = 1$ for all $n$.

Now, assume that $\sup_n \lambda_n < \infty$. 
Then, using the previous problem and strong law of large numbers we have that with 
probability $1$, 
$$
\lim_n \sum_{i=1}^n \frac{S_i \lambda_i}{n} = 1.0
$$
Let $\lambda_s = \sup_n \lambda_n$ then we have that
$$
\lim_n   \sum_{i=1}^n \frac{(S_i \lambda_i)/(\lambda_s^2)}{n} = \frac{1}{\lambda_s^2}
$$

However as $\lambda_s \geq \lambda_i$ for all $i$ we have that $\frac{\lambda_s S_i}{\lambda_i} \geq S_i$ for all $i$.
Thus, using a similar reasoning as above we must have that  $\sum_{i=1}^n \frac{S_i\lambda_i}{\lambda_s^2}$ diverges. However we know that $1/ \lambda_i \geq 1/\lambda_s$ for all $i$ and thus we have that for all $n$
$$
\begin{aligned}
\sum_{i=1}^n \frac{S_i}{\lambda_i} &\geq \sum_{i=1}^n \frac{S_i}{\lambda_s} \\\
&= \sum_{i=1}^n \frac{S_i \lambda_i}{\lambda_i \lambda_s} \\\
&\geq  \sum_{i=1}^n \frac{S_i \lambda_i}{\lambda_s^2} 
\end{aligned}
$$
And as this last series diverges then the series $\sum_{i=1}^n \frac{S_i}{\lambda_i}$ must also diverge. And so we are done. 

The last point to note is that we don't need the condition that $\sup_n \lambda_n < \infty$. 
Because all of the terms are positive it is easy to see that as long as there is any sub-sequence $\sigma_i$ of the $\lambda_i$  such that $\sup_n \lambda_{\sigma_i} < \infty$ then the series diverges as the proof goes through for that sub-sequence and the other terms are just positive.









<!--
</details> 
-->