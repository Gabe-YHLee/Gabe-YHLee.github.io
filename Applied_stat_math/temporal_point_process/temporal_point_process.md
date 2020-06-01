## Temporal Point Process (TPP)

A stochastic process modelling of the point patterns (a list of times of events) is a __temporal point process__. 

Denote the knowledge of all historical events up to time $t$ by 

$$
    \mathcal{H}_{t} = (..., t_1, t_2, ... , t_n)
$$ 

and Let $f(t_{n+1}|\mathcal{H}_{t_n})$ be the conditional density function of the time of the next event $t_{n+1}$ given the history of the previous events. Then the distribution of all events is given by the joint density

$$
    f(...,t_1, t_2, ...) = \Pi_{n} f(t_n | H_{t_{n-1}}).
$$

There is a convenient and intuitive way of specifying the TPP. Let $F(t|\mathcal{H}_{t_n})$ be a cumulative distribution function for any $t>t_n$. Then the __conditional intensity function (or hazard function)__ is defined by 

$$
    \lambda(t) = \frac{f(t|\mathcal{H}_t)}{1-F(t|\mathcal{H}_t)}.
$$

It can be heuristically interpreted as follows:<br>
$$\begin{aligned}
    \lambda(t)dt &= \frac{f(t|\mathcal{H}_t)dt}{1-F(t|\mathcal{H}_t)}\\
    &=\frac{\mathbb{P}(t_{n+1}\in[t,t+dt]|\mathcal{H}_{t_n})}{\mathbb{P}(t_{n+1})\notin (t_n,t)|\mathcal{H}_{t_n})} \\
    &= \mathbb{E}[N([t,t+dt])|\mathcal{H}_{t_n}],
\end{aligned}$$

where $N(-)$ denotes the number of points falling in an interval A. The popular poisson process is when $\lambda(t)=\lambda$.

Given the intensity function, we can compute back the conditional density function:

$$
    f(t|\mathcal{H}_{t_n}) = \lambda(t)\exp(-\int_{t_n}^t \lambda(s)ds),
$$

where $t_n$ is the last point before t.

__Marked Temporal Point Process__ is a temporal point process with more information associated with an event known as __marks__. For example, 

$$
    ..., (t_1,k_1), (t_2,k_2), ... , (t_n,k_n), ...
$$

is a sequence sampled from a __marked temporal point process__, where $t_i$ are the times of events and $k_i$ are the additional informations such as discrete values like event types or real values like locations. 

We can define the conditional intensity function in a similar manner as follows:

$$
    \lambda(t,k) = \lambda(t)f(k|t),
$$

where $\lambda(t)$ is called the ground intensity. 

### Likelihood Function
Given an unmarked point pattern $(t_1,...,t_n)$ on ab observation interval [0,T), the log likelihood function is given by

$$
    \log L = \sum_{i=1}^{n} \log \lambda(t_i)-\int_{0}^T\lambda(s)ds.
$$

Given a marked point patterns $((t_1,k_1),...,(t_n,k_n))$ on $[0,T) \times \mathbb{M}$, the log likelihood is given by

$$
    \log L = \sum_{i=1}^{n} \log f(k_i|t_i)+ \sum_{i=1}^{n} \log \lambda(t_i)-\int_{0}^T\lambda(s)ds.
$$

#### References
1. Rasmussen, Jakob Gulddahl. "Lecture notes: Temporal point processes and the conditional intensity function." arXiv preprint arXiv:1806.00221 (2018).

<div style="text-align: right"> June 1, 2020 </div>

[<u>back</u>](../../stat_and_math.md)