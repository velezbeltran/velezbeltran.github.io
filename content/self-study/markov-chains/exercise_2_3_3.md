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
\Pr\left( \sum_{n=1}^\infty S_n = \infty \right) = 1
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
\lim_n   \sum_{i=1}^n \frac{(S_i \lambda_i)/(\lambda_s)}{n} = \frac{1}{\lambda_s}
$$
Therefore, using the same reasoning as above we have that that the series $\sum_{i=1}^n S_i (\lambda_i / \lambda_s)$ diverges. However, we know that $\lambda_i / \lambda_s \leq 1$ for all $i$ and thus it must be that $\sum_{i=1}^n S_i$ diverges as well. And so we are done.

The condition $\sup_n \lambda_n < \infty$ is not necessary.
As a counter-example, assume that $\lambda_{2n}$ diverges and $\lambda_{2n + 1} = 1$ for all $n$. 
The, then clearly $\sum_{i=1}^n S_{2i + 1}$ diverges because of the previous argument. However, as $\sum_{i=1}^n S_{2i}$ is a series of positive terms then $\sum_i S_i$ must diverge as well. 





<!--
</details> 
-->