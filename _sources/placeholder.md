Some placeholder text
=======================

```{admonition} Learning goals
After reading this chapter, you will be able to
* recall what random variables are
* recall how to calculate expectation values of random variables and functions of random variables
* recall how to compute the variance of a random variable
* ...
```

##### Random variables
In statistical physics, we are interested in deriving macro-scale properties
from what we know about the micro-scale. Often, we are concerned with large
numbers of particles (or other things), and we apply the theory of probability
to find out how they behave on average.

An important concept in probability is _random variables_. A random variable does
not have a definite value, but rather a set of possible outcomes, each with a
certain probability. For example, a die can be represented by a random variable $X$
with outcomes $1, 2, 3, 4, 5$ and $6$, all with probability $1/6$.

```{admonition} Example
Another example of a random variable is the speed of molecules in an ideal gas. As you will be able
to derive later, the probability of finding a certain speed $v$ is given by

$$
  p(v) = \left( \frac{m}{2 \pi k T} \right)^{3/2} 4 \pi v^2 e^{-m v^2/2 k T},
$$

which is known as the Maxwell-Boltzmann distribution.
```

##### Expectation values
The expectation of a random variable is the average of its possible outcomes,
weighted by their probabilities. Mathematicians like to denote the expectation of
a random variable $X$ as $\mathbb{E}[X]$. In this course, we will use a notation
commonly used by physicists: $\langle X \rangle$.

If $X$ is a discrete random variable that can take values $x_1, x_2, ..., x_n$ with
corresponding probabilities $p_1, p_2, ..., p_n$, its expectation is given by

$$
  \langle X \rangle = \sum_{i=1}^n x_i p_i.
$$ (expectation_discrete)

If $X$ is a continuous random variable, the probability of getting an outcome $x$
is described by a probability density function $p(x)$. To be precise, the probability
for $X$ to take a value in the interval $[x, x+\mathrm{d}x]$ is $p(x)\mathrm{d}x$.
The sum in Equation {eq}`expectation_discrete` then becomes an integral, so that
the expectation for a continuous random variable $X$ is given by

$$
  \langle X \rangle = \int_{-\infty}^\infty x p(x) \mathrm{d}x.
$$ (expectation_continuous)

```{tip}
In practice, the same symbol is often used for the random variable and its
outcomes. For example, the expectation of the speed $v$ may be written as

$$\langle v \rangle = \int_{0}^\infty v p(v) \mathrm{d}v $$

(note that the speed -- the magnitude of the velocity -- is always positive, so $p(v)$ must be
zero for $v<0$, so the lower limit of the integral can be set to zero).
```

The expectation of a function of $X$, e.g. $g(X)$, is given by

##### Variance
The variance of a random variable is a measure of how much its outcomes deviate from the mean. With the notation common in mathematics, it is defined as

$$
    \mathrm{Var}[X] = \mathbb{E}[(X - \mathbb{E}[X])^2].
$$

In physics, we often denote the variance as the square of the standard deviation $\sigma$:

$$
    \sigma_X^2 = \langle(X-\langle X \rangle )^2 \rangle.
$$

By working out the square and using that the expectation is linear, you can rewrite the variance in the convenient form

$$
    \sigma_X^2 = \langle X^2\rangle - \langle X \rangle ^2.
$$ (variance_formula)
