## Variational Inference

Denote by $x$ an observable variable. A latent variable model (LVM) is a joint density $p(z,x)$ with a latent variable $z$. For example, Gaussian mixture model (GMM) is a latent variable model, where $x\in\mathbb{R}^{d}$ and $z \in \mathrm{Set}(1,2,...,K)$.

Given a set of observations $\mathrm{Set}(x_1,...,x_N)$, the inference problem is to compute the conditional density 

$$
    p(z|x)=\frac{p(z,x)}{p(x)}=\frac{p(z,x)}{\int p(z,x)d z}.
$$

For many models, the integral in the denominator is unavailable in closed form or requires exponential time to compute.

In variational inference, we posit a family of approximate conditional density functions $\mathcal{L}$, and the goal is to find the minimizer $q^*(z|x)$ of the following optimization problem:

$$
\begin{aligned}
q^*(z|x) &= \arg\min_{q(z|x)\in\mathcal{L}} \mathrm{KL}(q(z|x)||p(z|x)) \\
&= \arg\min_{q(z|x)\in\mathcal{L}} \mathbb{E}[\log \frac{q(z|x)}{p(z|x)}] \\
&= \arg\min_{q(z|x)\in\mathcal{L}} \mathbb{E}[\log q(z|x)]-\mathbb{E}[\log p(z,x)]+\log p(x) \\
&= \arg\min_{q(z|x)\in\mathcal{L}} \mathbb{E}[\log q(z|x)]-\mathbb{E}[\log p(z,x)],
\end{aligned}
$$

where all expectations are taken with respect to $q(z|x)$. Note that the above optimization problem is equivalent to maximizing the evidence lower bound (ELBO):
$$
\begin{aligned}
    \mathrm{ELBO}(q) &= \mathbb{E}[\log p(z,x)]-\mathbb{E}[\log q(z|x)]\\
    &= \mathbb{E}[\log p(x|z)]-\mathrm{KL}(q(z|x)||p(z)).
\end{aligned}
$$

Maximizing the ELBO has the following interpretations: i) the first term encourages to place their mass on configurations of the latent variables that explain the observed data, and ii) the second term encourages densities close to the prior. Thus the variational objective mirrors the usual balance between likelihood and prior.

Another property of the ELBO is the lower-boundess:

$$\begin{aligned}
    \log p(x) &= \mathrm{KL}(q(z|x)||p(z|x)) + \mathrm{ELBO}(q) \\
    &\geq \mathrm{ELBO}(q).
\end{aligned}$$

This relationship has led to using the variational bound as a model selection criterion for $p(x)$ under the premise that the bound is a good approximation of the marginal likelihood. Though this sometimes works in practice, selecting based on a bound is not justified in theory.

#### The mean-field variational family
TO BE UPDATED

#### References
1. Blei, David M., Alp Kucukelbir, and Jon D. McAuliffe. "Variational inference: A review for statisticians." Journal of the American statistical Association 112.518 (2017): 859-877.

<div style="text-align: right"> May 31, 2020 </div>

[<u>back</u>](../../ML.md)