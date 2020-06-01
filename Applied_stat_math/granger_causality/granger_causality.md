## Granger Causality

Granger causality is a statistical concept of causality that is based on prediction. According to Granger causality, if a signal $X_1$ "Granger-causes" (or "G-causes") a signal $X_2$, then past values of $X_1$ should contain information that helps predict $X_2$ above and beyond the information contained in past values of $X_2$ alone. 

Granger defined the causality relationship based on two principles:
1. The cause happens prior to its effect.
2. The cause has unique information about the future values of its effect.
Given these two assumptions about causality, Granger proposed to test the following hypothesis for identification of a causal effect of $X$ on $Y$:

$$
\mathbb{P}(Y(t+1)\in A|\mathcal{I}(t)) \neq \mathbb{P}(Y(t+1)\in A|\mathcal{I}_{-X}(t)),
$$

where $\mathbb{P}$ regers to probability, $A$ is an arbitrary non-empty set, and $\mathcal{I}(t)$ and $\mathcal{I}_{-X}(t)$ respectively denote the information available as of time $t$ in the entire universe, and that in the modified universe in which $X$ is excluded. If the above hypothesis is accepted, we say that $X$ Granger-causes $Y$.

#### References
1. http://www.scholarpedia.org/article/Granger_causality
2. https://en.wikipedia.org/wiki/Granger_causality

<div style="text-align: right"> June 1, 2020 </div>

[<u>back</u>](../../stat_and_math.md)