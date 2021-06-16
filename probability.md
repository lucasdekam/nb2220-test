# Probability

## Probability density function and moments

A probability density function should be normalised:

$$
  \int_{-\infty}^{\infty} P(x) \mathrm{d}x = 1
$$ (normalized_probability_density)

For simplicity we consider a probability density function of a single stochastic variable $X$ with a continuous set of potential outcomes $x$, but it could be generalised to multiple variables and discrete sets.

The $n^\mathrm{th}$ moment of this distribution is defined as:

$$
  \langle x^n \rangle \equiv \int_{-\infty}^{\infty} x^n P(x) \mathrm{d}x
$$ (moments)

The first and second moments are particularly useful, and yield the mean $\mu$ and standard deviation $\sigma$ of the distribution:

$$
  \mu = \langle x \rangle
$$ (mean_def)

$$
  \sigma = \sqrt{\langle x^2 \rangle - \langle x \rangle ^2}
$$ (stdev_def)

##### Central limit theorem
Given that $P(x)$ has a mean $\mu$ and a standard deviation $\sigma$, one can derive that the probability density function of the sum of many ourcomes of $X$ is a Gaussian distribution. Defining the sum of $n$ random variables as $X_1 + X_2 + ... + X_n = Y$, then

$$
  P(Y=y) \propto e^{\frac{(y - n \mu)^2}{2 n \sigma^2}}
$$ (clt)

with standard deviation $\sigma_Y = \sqrt{n} \sigma$ and mean $\mu_Y = n \mu$. This is independent of the form of the distribution of $X$, as long as $n$ is 'large'. What is called large may depend somewhat on the distribution, but usually, the number $10^{23}$ is more than sufficient. Another property of $P(y)$ is that the standard deviation becomes negligible compared to the mean, $\sigma_Y/\mu_Y \propto 1/\sqrt{n}$, such that a sample of $Y=y$ will almost certainly have the mean value as the outcome. This is one reason why the Gaussian distribution is so extremely important in the field of statistics. It appears everywhere, and tends to describe the properties of systems of many degrees of freedom (the velocity distribution in a gas, density fluctuations in a fluid, spatial fluctuations in a membrane, the 'shape' of a flexible polymer etc.).


## Problems

### Problem 1: Probability
Imagine that we could label and track the oxygen molecules in the air, and that we would label two of them inside a classroom. In the corner of the classroom is a box with a volume of about $0.1 \%$ of the total volume of the room. After some time someone takes a snapshot of where the molecules are at that point in time.
1. Assuming that the two molecules can be anywhere with equal probability, what would be the probability that they would both be inside the box?
2. What would be the probability that all the oxygen molecules would be inside the box? (Assume for simplicity that there are $10^{25}$ oxygen molecules in the room.)

### Problem 2: Probability density functions
A person throws with a perfect dice, i.e. each possible outcome $x \in {1, 2, ..., 6}$ has probability $P(x) = \frac{1}{6}$.
1. Calculate the expectation value of the outcome $\mu$. What is the most likely outcome? What is the standard deviation $\sigma$? What is $\sigma/\mu$? Draw the distribution.
