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
    sum. Now, solving the right hand side of {eq}`eq:average_energy`,
    one can use the chain rule

    $$
    \begin{aligned}
            -\frac{\partial}{\partial \beta} \ln{Z} &= -\frac{1}{Z}\frac{\partial Z}{\partial \beta}\\
            &= -\frac{1}{Z}\frac{\partial}{\partial \beta} \sum \limits_n e^{-\beta E_n}\\
            &= \frac{1}{Z} \sum \limits_n  E_n e^{-\beta E_n}
    \end{aligned}
    $$

    and the final expression is identical to {eq}`eq:average_energy_lhs`, which
    demonstrates the equality in {eq}`eq:average_energy`.

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

3.  To calculate the expectation value of the kinetic energy of all the
    particles, one has to evaluate, in principle

    $$\left\langle \sum \limits_{i=1}^N \frac{p_i^2}{2m} \right\rangle$$

    However, instead one only needs to calculate

    $$\left\langle \sum \limits_{i=1}^N \frac{p_i^2}{2m} \right\rangle = N \left\langle \frac{p_1^2}{2m} \right\rangle$$

    with

    $$
       \left\langle \frac{p_1^2}{2m} \right\rangle = \frac{ \int \frac{p_1^2}{2m} e^{-\beta \frac{p_1^2}{2m}} dp_1}{ \int e^{-\beta \frac{p_1^2}{2m}} dp_1}
    $$

    Argue why.

    The particles are identical, so there should not be a distinction
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

5.  If the particles are trapped in harmonic potential wells
    $V(x) = \frac{1}{2}kx^2$, what would be the average potential energy
    of one particle?

    $$\left \langle \frac{1}{2}kx^2  \right \rangle = \frac{ \int \frac{1}{2}kx^2 e^{-\beta \frac{1}{2}kx^2} dx}{ \int e^{-\beta \frac{1}{2}kx^2} dx}$$

    if everything worked out well, you found that for particles in
    harmonic wells

    $$\left \langle \frac{p^2}{2m} \right \rangle = \left \langle \frac{1}{2}kx^2 \right \rangle = \frac{1}{2}k_\mathrm{B}T$$

    This is called the <span>*equipartition theorem*</span>: any degree
    of freedom that appears as a quadratic term in the energy of a
    microstate, contributes $\frac{1}{2}k_\mathrm{B}T$ to the average
    energy. In this special case, the energy of each particle is equally
    divided between kinetic energy and potential energy, on average.

    And as if that is not puzzling enough, this situation is not
    artificial, but very common. In every solid, the atoms or molecules
    are trapped in some position, and vibrate at some location, in some
    potential well. Close to the minimum of that potential well, the
    potential is harmonic, regardless of the nature of the potential. If
    we make a Taylor expansion up to second order, around the minimum of
    the well $x_0$:

    $$V(x_0+x) = V(x_0) + V'(x_0) x + \frac{1}{2} V''(x_0) x^2$$

    then we can ignore the linear term in $x$, because $V'(x_0) = 0$ at
    the minimum, but $V''(x_0) \neq 0$, so that the potential is
    approximately harmonic (i.e. quadratic in $x$) close to its minimum,
    with “spring constant” $k = V''(x_0)$. So, in any solid at
    sufficiently low temperature, the equipartition theorem applies.

## Problem 5.4

1.  Calculate the probability $P(h)$ to find a particle at height $h$
    using the Boltzmann distribution.

    The probability of being in state $n$ is given by the Boltzmann
    distribution, equation [eq:Boltzmann~d~istribution~s~et~5~],

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

2.  Calculate the density of particles $\rho(h)$ at height $h$, using
    $\rho(h) = \rho_0 P(h)$, with $\rho_0 = N/V$ the average density

    This would be

    $$\rho(h) \propto e^{-\beta m g h}$$

    The proportionality constant could be obtained in different ways,
    e.g. if the concentration at a given height were known, or if the
    total number of particles was given.

3.  Find an expression for the length scale over which the density drops
    by a factor $e^{-1}\approx37\%$.

    In other words, find $L$ for which

    $$e^{-\beta mg(h+L)} = e^{-1}e^{-\beta mgh}$$

    This length scale is

    $$L = \frac{k_\mathrm{B}T}{mg}$$

4.  What would this length scale be for oxygen molecules, if the
    temperature of the air were 0 $^\mathrm{o}$C? You can use the
    following numbers:

    -   Avogadro’s number: $R_\mathrm{A}=6,022\cdot10^{23}$ (particles
        per mole)

    -   Boltzmann’s constant: $k_\mathrm{B} = 1.38\cdot10^{-23}$ (J
        K$^{-1}$)

    -   Mass oxygen: 16u or 16 g per mole

    Oxygen molecules have a mass $2 \cdot 16$ g/mole, and there are
    $6,022\cdot10^{23}$ particles per mole, so one oxygen molecule has a
    mass of $5,314\cdot10^{-26}$ kg. The corresponding length scale
    $L_\mathrm{O_2} = 7227$ m. This indicates why breathing at high
    altitude becomes more difficult, and why it can be dangerous to hike
    the Himalayas.

5.  What would this length scale be for spherical gold nanoparticles
    with a radius of $5$ nm in an aqueous solution? The mass density of
    gold is approximately $19.3\cdot10^3$ kg/m$^3$ (19 kg per liter).

    The mass of a single nanoparticle is $1,011\cdot10^{-20}$ kg, which
    is about a million times heavier than an oxygen molecule, so the
    length scale is also about a million times smaller, being around
    $L_\mathrm{AuNP} = 3,80$ cm. Still, this length scale is enormous
    compared to the size of a living cell. Besides, the mass density of
    organic components is much lower than that of gold, so you can see
    that gravity is of no influence on a cellular scale.

## Problem 5.5

A system that can exchange heat and particles with a reservoir is called
an “open system”, or a “$\mu,V,T$-ensemble”, or a “grand canonical
ensemble”. The terms are used as synonyms, but shed light on specific
properties of these systems. As an example of an open system, one can
consider the electrolytes in a hydrogel in contact with a salt buffer,
or the electrolytes in a solution of proteins in contact with a buffer,
separated by a semi-permeable membrane. Open systems are called “open”
because particles can float in and out, they have a chemical potential
$\mu$ and temperature $T$ fixed by a reservoir (a “buffer”), and obey
specific statistical properties. The probability that an open system is
in a state $m$ is given by

$$
    P(m) = \frac{1}{\mathcal{Z}}e^{-\beta E_m + \beta \mu N_m}
$$ (eq:Grand_canonical_distribution)

The expression looks similar to the Boltzmann distribution, equation
`eq`{eq:Boltzmann_distribution_set_5}, but with an extra term
$\beta \mu N_m$. It can be derived in a similar way as the Boltzmann
distribution. The chemical potential $\mu$ (the amount of energy needed
to add one particle to the system) is fixed by the reservoir, and
basically depends on the density of particles in the reservoir. The
number $N_m$ stands for the number of particles in the system, in state
$m$ (different states may have different numbers of particles, in
contrast to the $N,V,T$-ensemble). The factor $\mathcal{Z}$ is a
normalisation factor, given by

$$
    \mathcal{Z} = \sum \limits_m e^{-\beta E_m + \beta \mu N_m}
$$ (eq:Grand_partition_function)

and is called the “grand canonical partition function”. It seems an
inappropriately long name for a normalisation factor, but it is secretly
much more than that. A few properties will be explored in this exercise.

1.  Show that the average number of particles in an open system can be
    derived from $\mathcal{Z}$ by

    $$\langle N \rangle = k_\mathrm{B}T \frac{\partial}{\partial \mu} \ln{\mathcal{Z}}$$

    [hint: work out the right hand side and see that it results in the
    definition of the expectation value]

    A certain polymer has $M$ sites where particles can bind. It is in
    contact with a solution (the buffer) with a chemical potential $\mu$
    and temperature $T$. The binding energy of a particle to the polymer
    is $\epsilon$, such that the energy of a configuration of $N$
    particles on the polymer is simply

    $$E = N\epsilon$$

    In {eq}`eq:Grand_partition_function` the sum is over all
    states. In the following questions, this sum will be rewritten as a
    sum over $N$, the number of particles in the system. For that, one
    needs to know how many states there are with $N$ particles.

2.  How many different states are there given that $N$ particles are
    bound to the polymer? [Hint: in other words, in how many ways can
    $N$ identical particles bind to $M$ sites?]

3.  Show that $\mathcal{Z}$ can be rewritten as

    $$\mathcal{Z} = \sum \limits_{N=0}^M \binom{M}{N} \left( e^{-\beta(\epsilon - \mu)} \right)^N$$

4.  Use the relation

    $$\sum \limits_{N=0}^{M} \binom{M}{N} a^N b^{M-N} = (a + b)^M$$

    to derive that

    $$\mathcal{Z} = (e^{-\beta(\epsilon-\mu)} + 1)^M$$

5.  Find the average number of particles that bind to the polymer
    $\langle N \rangle$, as a function of $\mu$ and sketch this
    function. [hint: when sketching it may be useful to check the limits
    of $\mu \rightarrow \infty$ and $\mu \rightarrow -\infty$ and
    $\mu = \epsilon$, and to check whether those limits make sense]
