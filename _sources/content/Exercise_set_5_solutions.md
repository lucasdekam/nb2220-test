# Problem set 5

## Problem 5.2

1.  By definition, an expectation value is calculated by the sum (or
    integral) over all possible outcomes times their probability

    $$\langle E \rangle = \sum \limits_n E_n P(E_n).$$

    In this situation (an $N,V,T$-ensemble), the probability $P(E_n)$ is
    given by the Boltzmann distribution

    $$P(E_n) = \frac{1}{Z}e^{-\beta E_n}$$

    so, one can substitute this to obtain

    $$
            \langle E \rangle = \frac{1}{Z} \sum \limits_n E_n e^{-\beta E_n}
    $$ (eq:average_energy_lhs)

    The factor $Z$ does not depend on $n$, so it can be taken out of the
    sum. Now, solving the right hand side of equation {eq}`eq:average_energy`,
    one can use the chain rule

    $$
    \begin{aligned}
            -\frac{\partial}{\partial \beta} \ln{Z} &= -\frac{1}{Z}\frac{\partial Z}{\partial \beta}\\
            &= -\frac{1}{Z}\frac{\partial}{\partial \beta} \sum \limits_n e^{-\beta E_n}\\
            &= \frac{1}{Z} \sum \limits_n  E_n e^{-\beta E_n}
    \end{aligned}
    $$

    and the final expression is identical to equation {eq}`eq:average_energy_lhs`, which
    demonstrates the equality in equation {eq}`eq:average_energy`.

2.  The more difficult part of this exercise is to show

    $$\left \langle E^2 \right \rangle - \langle E \rangle^2= \frac{\partial^2}{\partial \beta^2} \ln {Z}$$

    which can be done in a similar way as in the previous question. The
    other equality follows immediately from the previous question, after
    adding another differential with respect to $\beta$. Starting with
    the right hand side, and using the rules of differentiation:

    $$
    \begin{aligned}
            \frac{\partial^2}{\partial \beta^2} \ln{Z} &= \frac{\partial}{\partial \beta} \left( \frac{1}{Z}\frac{\partial Z}{\partial \beta} \right)\\
            &= -\frac{1}{Z^2}\left(\frac{\partial Z}{\partial \beta}\right)^2 + \frac{1}{Z}\frac{\partial ^2 Z}{\partial \beta^2}
    \end{aligned}
    $$

    The first term can be recognized as $-\langle E \rangle^2$ (see
    previous question), and the second term results is equal to

    $$
    \begin{aligned}
             \frac{1}{Z}\frac{\partial ^2 Z}{\partial \beta^2} &= \frac{1}{Z} \frac{\partial^2}{\partial \beta^2}\sum \limits_n e^{-\beta E_n}\\
             &= \frac{1}{Z} \sum \limits_n E_n^2 e^{-\beta E_n}\\
             &= \sum \limits_n E_n^2 P(E_n)\\
             &= \left \langle E_n^2 \right \rangle
    \end{aligned}
    $$

    This completes the proof.

3.  One can use the result of previous question

    $$\sigma_E^2 = -\frac{\partial \langle E \rangle}{\partial \beta}$$

    and apply a substitution of variables,
    $\beta = \frac{1}{k_\mathrm{B}T}$:

    $$\frac{\partial \langle E \rangle}{\partial \beta} = \frac{\partial \langle E \rangle}{\partial T} \frac{\partial T}{\partial \beta}$$

    and calculate that

    $$\frac{\partial T}{\partial \beta} = -k_\mathrm{B}T^2$$

    This equation is an example of the so-called fluctuation-dissipation
    theorem.

## Problem 5.3

1.  This follows immediately from the rule that

    $$e^{a+b} = e^a e^b$$

2.  This statement follows immediately after using the previous question,
    and shuffling around some terms:

    $$\begin{aligned}
        Z &= \int e^{-\beta \sum \limits_{i=1}^N \left(\frac{p_n^2}{2m} + V(x_n)\right)}dx_1 dp_1 \cdots dx_N dp_N\\
        &= \int \prod \limits_{n=1}^N e^{-\beta \left(\frac{p_n^2}{2m} + V(x_n)\right)} dx_1 dp_1 \cdots dx_N dp_N\\
        &= \prod \limits_{n=1}^N \left ( \iint  e^{-\beta \left(\frac{p_n^2}{2m} + V(x_n)\right)} dx_n dp_n \right) \\
        &= \left( \int e^{-\beta V(x)} dx \int e^{-\beta \frac{p^2}{2m}} dp \right )^N
    \end{aligned}$$

    as requested.

3.  The particles are identical, so there should not be a distinction
    between any of the particles. Even though the kinetic energies can
    be different for a given microstate, the expectation value should be
    the same for each particle. This can also be verified
    mathematically, by writing out the expression. It will be done below
    for particle 1. Writing out the full expression of the expectation
    value

    $$
    \begin{aligned}
        \left \langle \frac{p_1^2}{2m} \right \rangle &=& \frac { \int \frac{p_1^2}{2m} e^{-\beta \sum \limits_{i=1}^N \left(\frac{p_n^2}{2m} + V(x_n)\right)}dx_1 dp_1 \cdots dx_N dp_N } { \int e^{-\beta \sum \limits_{i=1}^N \left(\frac{p_n^2}{2m} + V(x_n)\right)}dx_1 dp_1 \cdots dx_N dp_N }
    \end{aligned}
    $$

    Using the result of previous question, one can factorise the
    integrals and obtain

    $$
    \begin{aligned}
        \left \langle \frac{p_1^2}{2m} \right \rangle &=& \frac { \int \frac{p_1^2}{2m} e^{-\beta \frac{p_n^2}{2m}} dp_1 \int e^{-\beta V(x)} dx_1 \left( \int e^{-\beta V(x)} dx \int e^{-\beta \frac{p^2}{2m}} dp \right )^{N-1} } { \left( \int e^{-\beta V(x)} dx \int e^{-\beta \frac{p^2}{2m}} dp \right )^N } \\
        &= \frac{ \int \frac{p_1^2}{2m} e^{-\beta \frac{p_1^2}{2m}} dp_1}{ \int e^{-\beta \frac{p_1^2}{2m}} dp_1}
    \end{aligned}
    $$

4.  Direct evaluation of the integral, using the properties of a
    Gaussian integral

    $$\int \limits_{-\infty}^\infty e^{-a p^2} dp = \sqrt{\frac{\pi}{a}}$$

    and

    $$\int \limits_{-\infty}^\infty p^2 e^{-a p^2} dp = \frac{1}{2a} \sqrt{\frac{\pi}{a}}$$

    should yield

    $$\left \langle \frac{p^2}{2m} \right \rangle = \frac{1}{2}k_\mathrm{B}T$$

    In 3 dimensions, this value would be $\frac{3}{2}k_\mathrm{B}T$.

    So, temperature relates directly to the kinetic energy of the
    particles, i.e. how fast they move and vibrate. This is independent
    of how the particles interact, or other properties of the system. It
    is a universal relation.

5.  ...

## Problem 5.4

1.  The probability of being in state $n$ is given by the Boltzmann
    distribution, equation {eq}`Boltzmann_distribution_set_5`,
    
    $$P(n) = \frac{1}{Z}e^{-\beta E_n}$$

    The state is in this case determined by all the positions and
    momenta of all the particles,

    $$P(r_1,p_1,r_2,p_2,...,r_N,p_N)=\frac{1}{Z}e^{-\beta E(r_1,p_1,r_2,p_2,...,r_N,p_N)}$$

    and the energy is just a sum of terms, similar to the previous
    exercise

    $$E(r_1,p_1,r_2,p_2,...,r_N,p_N) = \sum \limits_{n=1}^{N} \frac{p_n^2}{2m} + mgh_n$$

    with $h_n$ the height of particle $n$ (the other coordinates do not
    change the energy, only the height matters). If one is only
    interested in a single particle, and not in all the other particles,
    one needs to integrate over all the other degrees of freedom, and
    then one obtains

    $$P(h) \propto e^{-\beta m g h}$$

    [Check why this only works if the particles do not interact with
    each other: in that case the energy would also depend on the
    relative positions of the particles, and contain terms of the form
    $V(|r_i - r_j|)$, and that complicates the derivation of $P(h)$
    significantly]

2.  This would be

    $$\rho(h) \propto e^{-\beta m g h}$$

    The proportionality constant could be obtained in different ways,
    e.g. if the concentration at a given height were known, or if the
    total number of particles was given.

3.  In other words, find $L$ for which

    $$e^{-\beta mg(h+L)} = e^{-1}e^{-\beta mgh}$$

    This length scale is

    $$L = \frac{k_\mathrm{B}T}{mg}$$

4.  Oxygen molecules have a mass $2 \cdot 16$ g/mole, and there are
    $6,022\cdot10^{23}$ particles per mole, so one oxygen molecule has a
    mass of $5,314\cdot10^{-26}$ kg. The corresponding length scale
    $L_\mathrm{O_2} = 7227$ m. This indicates why breathing at high
    altitude becomes more difficult, and why it can be dangerous to hike
    the Himalayas.

5.  What would this length scale be for spherical gold nanoparticles
    with a radius of 5 nm in an aqueous solution? The mass density of
    gold is approximately $19.3\cdot10^3$ kg/m$^3$ (19 kg per liter).

    The mass of a single nanoparticle is $1,011\cdot10^{-20}$ kg, which
    is about a million times heavier than an oxygen molecule, so the
    length scale is also about a million times smaller, being around
    $L_\mathrm{AuNP} = 3,80$ cm. Still, this length scale is enormous
    compared to the size of a living cell. Besides, the mass density of
    organic components is much lower than that of gold, so you can see
    that gravity is of no influence on a cellular scale.

## Problem 5.5

...
