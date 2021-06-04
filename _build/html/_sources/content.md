Chapter 1: Probability recap
=======================

## 1.1 Expectation values
The expectation of a random variable is the average of its possible outcomes,
weighted by their probabilities. Mathematicians like to denote the expectation of
a random variable $X$ as $\mathbb{E}[X]$. In this course, we will use the notation
preferred by physicists: $\langle X \rangle$.

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
