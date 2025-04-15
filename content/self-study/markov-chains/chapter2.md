---
title: "Chapter 2: Continuous Time MCs"
weight: 1
date: "2025-04-16"
math: True
---

As titled! A variety of problems on continious time markov chains. 
Mostly, set-up. 

## Exercise 1

Suppose $S$ and $T$ are independent exponential random variables of parameters $\alpha$ 
and $\beta$ respectively. 
- What is the distribution of $\min \\{ S, T\\}$? 
- What is the probability that $S \leq T$? 
- Show that the two events $\\{S \leq T\\}$ 
 and $\\{\min\\{S, T\\} \geq t\\}$ are independent. 

<!--
<details>
<summary><strong>Solution</strong></summary>
--> 

1. For the first problem we use the CDF trick. 
Concretely, call $Y = \min\\{S, T\\}$ then: 
$$
\begin{aligned}
P( Y \leq y ) &= 1 - P\left( Y > y \right) \\\
                &= 1 - P\left( S > y , T > y \right) \\\
                &= 1 - P(S > y) \P(T > y) \\\
                &= 1 - e^{-\alpha y} e^{-\beta y} \\\
                &= 1 - e^{-(\alpha + \beta)y}
\end{aligned}
$$
This is clearly the CDF of an exponential variable $\text{Exp}(\alpha + \beta)$.

2. The second problem can be solved by applying conditional expectations:
$$
\begin{aligned}
    P( S \leq T) = \E[ \E[ S \leq T \mid T ]]
\end{aligned}
$$

<!-- </details> -->