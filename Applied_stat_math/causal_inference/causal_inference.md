## Causal Inference

If two things, A and B are dependent, then either: 
* A causes B or,
* B causes A or,
* something else causes both A and B.

#### The three tasks of data science
1. **Description** : What is there?
2. **Prediction** : What will happen?
3. **Causal Inference** : What would happen? 

#### Structural Causal Models: Example
Given two random variables, $X$,$Y$, when $X$ causes $Y$, it is expressed as: $X=f_X(U_X)$, $Y=f_Y(X,U_Y)$, where $U_X$ and $U_Y$ are some unknown random variables. This structural model yields a probability density function on $(X,Y)$, $P(X,Y)$. Then, finally, samples $(x_i,y_i), i=1,...,N$ are drawn from $p(X,Y)$. 

From a set of samples, the process of estimating $p(X,Y)$ is a statistical inference, and the process of estimating $f_X,f_Y$ is a causal inference.

#### References
1. https://www.youtube.com/watch?v=dFp2Ou52-po ("What is causal inference, and why should data scientists know? by Ludvig Hult")

<div style="text-align: right"> June 1, 2020 </div>

[<u>back</u>](../../stat_and_math.md)