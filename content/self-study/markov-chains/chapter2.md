---
title: "Chapter 2 – Continuous Time Markov Chains"
weight: 1
math: True
---


### Exercise 1
**Problem:**
Suppose $S$ and $T$ are independent exponential random variables of parameters $\alpha$ 
and $\beta$ respectively. 
- What is the distribution of $\min \\{ S, T\\}$? 
- What is the probability that $S \leq T$? 
- Show that the two events $\\{S \leq T\\}$ 
 and $\\{\min\\{S, T\\} \geq t\\}$ are independent. 

**Solution:**
For the first problem we use the CDF trick. 
Concretely, call $Y = \min\\{S, T\\}$ then: 
$$
\begin{aligned}
\Pr( Y \leq y ) &= 1 - \Pr\left( Y > y \right) \\\
                &= 1 - \Pr\left( S > y , T > y \right) \\\
                &= 1 - \Pr(S > y) \Pr(T > y) \\\
                &= 1 - e^{-\alpha y} e^{-\beta y} \\\
                &= 1 - e^{-(\alpha + \beta)y}
\end{aligned}
$$
This is clearly the CDF of an exponential variable $\text{Exp}(\alpha + \beta)$.