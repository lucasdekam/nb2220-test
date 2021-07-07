(ch:chapter1)=
# Large numbers

```{admonition} Learning goals
After reading this chapter, you will be able to
* ...
```

(sec:Oxygen_in_Box)=
## Probability

Imagine that we could label and track the oxygen molecules in the air,
and that we would label two of them inside a classroom. In the corner of
the classroom is a box with a volume of about $0.1\%$ of the total
volume of the room. After some time someone takes a snapshot of where
the molecules are at that point in time.

1.  Assuming that the two molecules can be anywhere with equal
    probability, what would be the probability that they would both be
    inside the box?

2.  What would be the probability that all the oxygen molecules would be
    inside the box? (assume for simplicity that there are $10^{25}$
    oxygen molecules in the room)

3.  If the answer under b) was expressed as a fraction, then the
    denominator should be a large number. Compare this number to the
    total number of grains of sand on Earth ($\mathcal{O}(10^{18})$) and
    the total number of elementary particles in the visible Universe
    (roughly $10^{70}$ plus or minus a few orders of magnitude) and
    comment.

4.  Imagine that the distribution of oxygen molecules would completely
    randomise every hour, would you be afraid that this situation would
    occur during the lifetime of the universe? (around $10^{14}$ hours)

5.  Even if the position of the molecules would randomize every
    femtosecond, show that it would not matter for the previous answer.

6.  A thousand proteins of a certain kind are located inside a cell.
    What would be the probability that they would all be in a small
    corner of the cell, with a volume of about $1\%$ of the total
    volume, under the same assumptions as before? Which assumption would
    be troublesome and why? (give at least two reasons)

(sec:Central_limit_theorem_dice)=
## Probability density distributions

A person throws with a perfect dice, i.e. each possible outcome
$x \in \{1,2,\ldots ,6\}$ has probability $P(x)=\frac{1}{6}$.

1.  Calculate the expectation value of the outcome $\mu$. What is the
    most likely outcome? What is the standard deviation $\sigma$? What
    is $\sigma/\mu$? Draw the distribution.

2.  Do the same but now for two dice (so for $P(X_1+X_2 = y)$, where
    $y\in \{2,3,\ldots,12\}$). Divide the standard deviation $\sigma_2$
    by the standard deviation $\sigma$ for 1 dice, and check that the
    number is close to $\sqrt{2}$.

3.  Do the same as in b) but now for three dice. Be welcome to estimate
    the standard deviation, instead of calculating it.

4.  Do the same but now for $N=100$ dice. Determine the standard
    deviation. A sketch of the distribution with the appropriate
    standard deviation would suffice.

5.  Do the same as in d) but now for $N=10^{12}$ dice.

(sec:Orders_of_magnitude)=
## Orders of magnitude

1.  Estimate the number of water molecules inside a cell. Be welcome to
    pick convenient numbers, as long as the order of magnitude is
    correct. (Computer simulations typically can handle several
    thousands of particles, or an order of magnitude more if run on a
    cluster for high-performance computation)

2.  Estimate the number of cells inside the human body.

3.  Estimate the number of lipid molecules inside a single cell
    membrane.

4.  Estimate the number of microbes on our skin.

(sec:Emergent_behavior)=
## Emergent behavior

Are the following phenomena emergent or not? If so, explain where they
come from (i.e. mention a lower level phenomenon / microscopic
mechanism, or multiple levels).

1.  Temperature

2.  Brownian motion

3.  The elasticity of a cell membrane

4.  Cell division

5.  Thoughts

6.  Music

7.  Awareness

(sec:Notes_Central_limit_theorem)=
## Useful notes and equations

A probability density function should be normalized:

$$
  \int \limits_{-\infty}^{\infty} P(x) dx = 1.
$$ (eq:pdf_normalized)

For simplicity we consider a probability density function of a single stochastic variable
$X$ with a continuous set of potential outcomes $X=x$, but it could be
generalized to multiple variables and discrete sets.

The $n^{\mathrm{th}}$ moment of this distribution is defined as

$$
  \langle x^n \rangle \equiv     \int \limits_{-\infty}^{\infty} x^n P(x) dx.
$$ (eq:moments)

The first and second moment are particularly useful, and yield the mean
$\mu$ and the standard deviation $\sigma$ of the distribution,

$$
  \mu = \langle x \rangle
$$ (eq:mean)

and

$$
  \sigma = \sqrt{ \langle x^2 \rangle - \langle x \rangle^2 }.
$$ (eq:stdev)

The Fourier transform of $P$ is known as the characteristic function of
$P$,

$$
  G(k) \equiv \int P(x) e^{ikx} dx,
$$ (eq:characteristic_function)

and the Taylor expansion of
$G(k)$ yields the moments of $P$. We will not use the characteristic
function in this course, although it is useful if one wants to derive
the central limit theorem, given below {cite:p}`van1992stochastic`.

### Central limit theorem (a short version)

Given that $P(x)$ has a mean $\mu$ and a standard deviation $\sigma$,
one can derive that the probability density function of the sum of many
outcomes of $X$ is a Gaussian distribution. Defining the sum of $n$
outcomes as $X_1+X_2+ \ldots + X_n = Y$, then

$$
  P(Y=y) \propto e^{-\frac{(y-n\mu)^2}{2n\sigma^2}}
$$ (eq:clt)

with standard
deviation $\sigma_y = \sqrt{n} \sigma$ and mean $\mu_y = n \mu$. This is
independent of the form of the distribution of $X$, as long as $n$ is
'large'. What is called large may depend somewhat on the distribution,
but usually, the number $10^{23}$ is more than sufficient.

Another
property of $P(y)$ is that the standard deviation becomes negligible
compared to the mean, $\sigma_y / \mu_y \propto 1/\sqrt{n}$, such that a
sample of $Y=y$ will almost certainly have the mean value as the
outcome. This is one reason why the Gaussian distribution is so
extremely important in the field of statistics. It appears everywhere,
and tends to describe the properties of systems of many degrees of
freedom (the velocity distribution in a gas, density fluctuations in a
fluid, spatial fluctuations in a membrane, the 'shape' of a flexible
polymer &c.).

## References
```{bibliography}
:style: unsrt
:filter: docname in docnames
```
