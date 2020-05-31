## Normalizing Flows

A normalizing flow is a transformation of a simple probability distribution (e.g., a standard normal) into a more complex distribution by a sequence of invertible and differentialbe mappings.

Let $Z\in \mathbb{R}^D$ be a random variable with a known and tractable probability density function $p_Z$. Let $g$ be an invertible function and $Y=g(Z)$. Then using the change of variables formula, one can compute the probability density function of the random variable $Y$: 
$$p_Y(y) = p_Z(f(y))|\det Dg(f(y))|^{-1},$$ 
where $f = g^{-1}$, and $Dg(z)=\frac{\partial g}{\partial z}(z)$ is the Jacobian of $g$. This new density function $p_Y$ is called a pushforward of the density $p_Z$ by function $g$ and denoted by $g_* p_Z$. 

Normalizing Flows (NF) are a family of generative models with tractable distributions where both sampling and density evaluation can be efficient and exact. 
* **The generative direction**: To generate a data point $y$, one can sample $z$ from $p_Z$, and then apply the above function $g$ called a generator.
* **The normalizing direction**: Given an observation $y$ from a complicated and irregular data distribution $p_Y$, apply the inverse function $f$ towards the simpler, more regular or “normal” form $p_Z$. Then, we can explicitly evaluate $p_Y(y)$. 

If the transformation $g$ can be arbitrarily complex, one can generate any distribution $p_Y$ from any base distribution $p_Z$ under reasonable assumptions on the two distributions. This has been proven formally.

By the term Normalizing Flows people mean bijections which are convenient to compute, invert, and calculate the determinant of their Jacobian. Normalizing Flows should satisfy several conditions in order to be practical. They should:
* be invertible; for sampling we need g while for computing likelihood we need f,
* be sufficiently expressive to model the distribution of interest,
* be computationally efficient, both in terms of computing f and g (depending on the application) but also in terms of the calculation of the determinant of the Jacobian.

### Examples flows
#### Elementwise FLows
TO BE UPDATED

#### References
1. Kobyzev, Ivan, Simon Prince, and Marcus Brubaker. "Normalizing flows: An introduction and review of current methods." IEEE Transactions on Pattern Analysis and Machine Intelligence (2020).

<div style="text-align: right"> May 31, 2020 </div>

[<u>back</u>](../../ML.md)