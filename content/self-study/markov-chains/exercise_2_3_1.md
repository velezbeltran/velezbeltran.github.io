---
title: "Exercise 2.3.1"
weight: 2
date: "2025-04-14"
math: true
draft: false
---

Suppose $S$ and $T$ are independent exponential random variables of parameters $\alpha$ 
and $\beta$ respectively. 
- What is the distribution of $\min \\{ S, T\\}$? 
- What is the probability that $S \leq T$? 
- Show that the two events $\\{S \leq T\\}$ 
 and $\\{\min\\{S, T\\} \geq t\\}$ are independent. 


# Solution
<!--
<details>
<summary><strong>Solution</strong></summary>
-->

1. For the first problem we use the CDF trick. 
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

2. The second problem can be solved by applying conditional expectations:
$$
\begin{aligned}
    \Pr( S \leq T) &= \E[ \E[ S \leq T \mid T ]] \\\
    &= \int_0^\infty \E [ S \leq T \mid T  = t] \beta \exp(-\beta t) dt\\\
    &= \int_0^\infty \\left(1 - \exp(-\alpha t)\\right) \beta \exp(-\beta t) dt\\\\
    &= \int_0^\infty \\left(\beta \exp(-\beta t) - \beta \exp(-(\alpha + \beta) t)\\right)  dt\\\
    &= 1 - \frac{\beta}{\alpha + \beta}\\\
    &= \frac{\alpha}{\alpha + \beta}
\end{aligned}
$$

3. We use the same "trick" as above. Concretely we see that 
$$
\begin{aligned}
 \Pr(S \leq T \text{ and } S, T \geq t) &= \E[\E[ S \leq T \text{ and } S, T \geq t\mid S] ]\\\
 &= \int_t^\infty \E[ S \leq T \text{ and } S, T \geq t\mid S= s]  \alpha e^{-\alpha s} ds\\\
\end{aligned}
$$
Now, clearly the issue is to find
$$
\E[ S \leq T \text{ and } S, T \geq t\mid S= s]
$$
But this is easy. When $s \geq t$ we see that only the left side matters and the value is $\exp(-\beta s)$.
Therefore, because in the integral $s$ is always greater than $t$, we have
$$
\begin{aligned}
\Pr(S \leq T \text{ and } S, T \geq t) &= \int_t^\infty e^{-\beta s} \alpha e^{-\alpha s} ds\\\
&= \int_t^\infty \alpha e^{-(\alpha + \beta) s} ds\\\
\end{aligned}
$$
Evaluating this integral is easy because we know that 
$$
\int (\alpha + \beta) e^{-(\alpha + \beta) s} ds = \exp(-(\alpha + \beta) s)
$$
Hence, multiplying both sides by $\frac{\alpha}{\alpha + \beta}$ we have
$$
\int_t^\infty \alpha e^{-(\alpha + \beta) s} ds = \exp(-(\alpha + \beta) t) \frac{\alpha}{\alpha + \beta}
$$
We see then that this implies the independence because the left side is $\Pr(S \leq T)$ and the right side is $\Pr(\min\\{S, T\\} \geq t)$, according to the first part of the problem.

<!--
</details> 
-->

