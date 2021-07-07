# Distributions

## Short summary of important terms

A system with volume $V$ and number of particles $N$, in thermal contact
with a large reservoir with temperature $T$ is described by the
Helmholtz free energy $F(N,V,T)$ and

$$
    F = E - TS
$$

with $E$ the energy of the system and $S$ the entropy. Boltzmann defined the entropy to be

$$
  S(E) = k_\mathrm{B} \ln{\Omega(E)}
$$

with $\Omega(E)$ the number of
microstates with energy $E$. From this definition, it follows that the
entropy is extensive. The temperature is defined as

$$
  \frac{\partial S}{\partial E} = \frac{1}{T}
$$

which may look abstract,
but it contains all the intuitive properties that we associate with
temperature (homework set 4 derived an important one). A fundamental
assumption in statistical physics is that

> In a closed system, each microstate is equally probable.

A closed system has a fixed energy $E(N,V,S)$. In statistical physics a
closed system is sometimes referred to as a "microcanonical ensemble".
The fundamental assumption does not apply to systems that are in thermal
contact with a large reservoir, that is, an "$(N,V,T)$-ensemble". The
probability to find such a system in state $n$, with energy $E_n$ is
given by the Boltzmann distribution

$$
    P(n) = \frac{1}{Z} e^{-\beta E_n},
$$ (eq:Boltzmann_distribution_set_5)

with $\beta = 1/k_\mathrm{B}T$.
The normalisation constant

$$
    Z = \sum \limits_n e^{-\beta E_n}
$$

is called the partition function. The $(N,V,T)$-ensemble is also called the
\"canonical ensemble\". The Helmholtz free energy can be written as
(skipping the derivation, but it can be found in David Tong, chapter 1)

$$
    F = - k_\mathrm{B}T \ln{Z}
$$

from which all kinds of useful properties
of the system can be derived. The partition function $Z$ gives all the
information of a system in thermodynamic equilibrium. However, in many
cases $Z$ is very difficult (if not impossible) to calculate. There are
many beautiful methods to approximate $Z$, and to calculate the
thermodynamic properties of complex systems. We will not have time to
study these methods in this course.

States can be labeled in different ways. Here we pretend that we can
count all the states with a label $n$ and energy $E_n$, for simplicity.
In many cases, a state is characterized by all the positions of the
particles, so that instead of the label $n$, the state is described by a
large vector $\vec{\Gamma} = (\vec{r}_1,\vec{r}_2,...,\vec{r}_N)$. In
that case, one has to integrate over all possible positions of the
particles, and that is in general a difficult task if the particles are
interacting with each other. For an ideal gas, in which the particles do
not interact, the situation is much simpler. In the exercise
{ref}`sec:Random_walk_part_II` a polymer was considered as "the
system" and the surrounding solvent as a temperature reservoir. Each
state was characterized by the orientation of all the segments of the
polymer. There are many situations where polymers behave as "ideal
polymers", i.e. where the segments do not interact with each other and
can be oriented in any direction with equal probability, independent of
what their neighbors are doing.

The Boltzmann distribution will be needed in the following exercises,
and in the rest of the course. In this set you will derive an example of
the so-called "fluctuation-dissipation theorem", i.e. how energy
fluctuations in the system are related to the ability of the system to
dissipate heat. You will also see that the temperature of a system is
directly coupled to the kinetic energy of its particles

$$
  \left\langle \frac{1}{2}mv^2 \right\rangle = \frac{3}{2}k_\mathrm{B}T
$$

and derive the "equipartition theorem", i.e. that the energy of the
particles in a solid is equally distributed between kinetic energy and
potential energy (on average, and under the right circumstances).

## The fluctuation-dissipation theorem

The energy in the canonical ensemble can fluctuate, because of heat
exchange between the system and the reservoir.

1.  Show that in the canonical ensemble ($N,V,T$-ensemble) the
    expectation value of the energy obeys

    $$
        \langle E \rangle = -\frac{\partial}{\partial \beta} \ln{Z}
    $$

    with $Z$ the partition function.

2.  Show that the fluctuations in the energy (in other words, the
    standard deviation) is

    $$
        \sigma_E^2 = \langle E^2 \rangle - \langle E \rangle^2 = \frac{\partial^2}{\partial \beta^2} \ln {Z} = -\frac{\partial \langle E \rangle}{\partial \beta}.
    $$

    The heat capacity $C_V = \partial \langle E \rangle / \partial T$ is
    the amount of energy required to raise the temperature of the system
    (usually expressed in Joule per Kelvin). The subscript $V$ in $C_V$
    emphasizes that the volume of the system is fixed, which is
    appropriate for this system. (There is a different expression for
    $C_p$.)

3.  Show that

    $$
        \sigma_E^2 = k_\mathrm{B}T^2 C_V.
    $$

    You just derived an
    example of the so-called *fluctuation-dissipation theorem*.
    Fluctuations in the energy of the system (left hand side) are
    related to its heat capacity (right hand side), that is, the ability
    to absorb / dissipate energy. The larger the heat capacity of a
    system is, the more energy the system needs to raise the
    temperature, and according to this equation, the more the energy can
    fluctuate.

## Temperature and equipartition

In classical mechanics, one has to solve a lot of questions about
colliding billiard balls, accelerating cars, boxes being dropped from
airplanes, rolling cylinders, &c. In situations where friction can be
ignored, one can use a very useful theorem, that the total energy is
conserved. This theorem follows directly from Newton's laws of motion.
This concept was an inspiration, two centuries later, to define the
first law of thermodynamics. Even later, Boltzmann united the "energy"
in classical mechanics with the "energy" in thermodynamics as the same
concept, the energy of a fluid being nothing but the energy (from
classical mechanics) of all the particles together. This made the
meaning of "energy" more concrete and straightforward.

According to classical mechanics, a particle moving in 1 dimension has
total energy

$$
  E = \frac{1}{2}mv^2 + V(x) = \frac{p^2}{2m} + V(x)
$$

The first term represents the kinetic energy of the particle, the second the
potential energy. The potential energy could originate from gravity
$V(x)=mgx$ or a spring $V(x)=\frac{1}{2}kx^2$, for example. One can
rewrite the equation in terms of momentum $p=mv$. If one wants to write
down the total energy of $N$ non-interacting particles in a fluid, the
expression is almost the same, except for a summation sign:

$$
    E = \sum \limits_{i=1}^N \left(\frac{p_i^2}{2m} + V(x_i)\right)
$$ (eq:Total_energy_Hamiltonian)

One simply sums the total energy of each particle. The term
"non-interacting" is important here, otherwise the expression becomes
more complicated. In that case one would have to add another term, an
interaction term

$$
    V_\mathrm{int} = \sum \limits_{i=j+1}^N \sum \limits_{j=1}^N V(|x_i - x_j|)
$$

One can generalize the situation also to three dimensions, but to keep
the notation simple, we will focus on one dimension for now, and use
equation {eq}`eq:Total_energy_Hamiltonian`.

If we enclose these particles in a volume $V$ coupled to a thermal
reservoir (that is, we create a canonical ensemble) then we can
calculate the probability to find the system in a certain configuration
$\vec{\Gamma} = (x_1, p_1, x_2, p_2, ..., x_N, p_N)$, thanks to the
Boltzmann distribution, equation {eq}`eq:Boltzmann_distribution_set_5`:

$$
    P(\vec{\Gamma}) = \frac{1}{Z} e^{-\beta E(\vec{\Gamma})}.
$$

The energy
depends now on $\vec{\Gamma}$, that is, all the positions and momenta of
the particles. It makes the notation less pretty, but wait until you see
the next equation. In case this is the first time you see the
expression, I would like to ask for your tolerance, and can assure that
it will grow on you. It will be more than sufficient if you understand
conceptually what is going on. The notational difficulty is that we have
to replace the sum over $n$ by integrals over all positions $x_i$ and
momenta $p_i$, if one wants to evaluate $Z$:

$$
\begin{aligned}
    Z &= \int e^{-\beta E(\vec{\Gamma})}d\vec{\Gamma}\\
    &= \int e^{-\beta \sum \limits_{i=1}^N \left(\frac{p_i^2}{2m} + V(x_i)\right)}dx_1 dp_1 \cdots dx_N dp_N.
\end{aligned}
$$ (eq:Partition_sum_Hamiltonian)

Conceptually, the expression is not as complicated as it looks: one
rearranges the particles in all possible ways, with all possible
momenta, and sums (integrates) all the $e$-factors. Equation
{eq}`eq:Partition_sum_Hamiltonian` is a $2N$-dimensional
integral, over all the positions $x_i$ and momenta $p_i$ of $N$
particles. In practice we can use clever tricks to deal with this
integral.

1.  Show that

    $$
        e^{-\beta \sum \limits_{i=1}^N \left(\frac{p_i^2}{2m} + V(x_i)\right)} = \prod \limits_{i=1}^N e^{-\beta \left(\frac{p_i^2}{2m} + V(x_i)\right)}.
    $$

2.  Argue that the intimidating expression, equation {eq}`eq:Partition_sum_Hamiltonian`, is just
    the product of $N$ identical terms, and that one only needs to calculate

    $$
        \left( \int e^{-\beta V(x)} dx \int e^{-\beta \frac{p^2}{2m}} dp \right )^N.
    $$

3.  To calculate the expectation value of the kinetic energy of all the
    particles, one has to evaluate, in principle

    $$
        \left\langle \sum \limits_{i=1}^N \frac{p_i^2}{2m} \right\rangle.
    $$

    However, instead one only needs to calculate

    $$
        \left\langle \sum \limits_{i=1}^N \frac{p_i^2}{2m} \right\rangle = N \left\langle \frac{p_1^2}{2m} \right\rangle
    $$

    with

    $$
    \begin{aligned}
        \left\langle \frac{p_1^2}{2m} \right\rangle = \frac{ \int \frac{p_1^2}{2m} e^{-\beta \frac{p_1^2}{2m}} dp_1}{ \int e^{-\beta \frac{p_1^2}{2m}} dp_1}.
    \end{aligned}
    $$

    Argue why.

4.  Evaluate this integral, using the following properties of a Gaussian integral:

    $$
        \int \limits_{-\infty}^\infty e^{-a p^2} dp = \sqrt{\frac{\pi}{a}}
    $$

    and

    $$
        \int \limits_{-\infty}^\infty p^2 e^{-a p^2} dp = \frac{1}{2a} \sqrt{\frac{\pi}{a}}.
    $$

    If everything worked out well, you found that the mean kinetic
    energy of a particle is

    $$
        \left \langle \frac{p^2}{2m} \right \rangle = \frac{1}{2}k_\mathrm{B}T.
    $$

    In 3 dimensions, this value would be $\frac{3}{2}k_\mathrm{B}T$. So,
    temperature relates directly to the kinetic energy of the particles,
    i.e. how fast they move and vibrate. This is independent of how the
    particles interact, or other properties of the system. It is a
    universal relation.

5.  If the particles are trapped in harmonic potential wells
    $V(x) = \frac{1}{2}kx^2$, what would be the average potential energy
    of one particle?

    <!-- Add a sentence introducing the formula below? -->

    $$
        \left \langle \frac{1}{2}kx^2  \right \rangle = \frac{ \int \frac{1}{2}kx^2 e^{-\beta \frac{1}{2}kx^2} dx}{ \int e^{-\beta \frac{1}{2}kx^2} dx}
    $$

    If everything worked out well, you found that for particles in
    harmonic wells

    $$
        \left \langle \frac{p^2}{2m} \right \rangle = \left \langle \frac{1}{2}kx^2 \right \rangle = \frac{1}{2}k_\mathrm{B}T.
    $$

    This is called the *equipartition theorem*: the energy of each
    particle is equally divided between kinetic energy and potential
    energy, on average.

    And as if that is not puzzling enough, this situation is not
    artificial, but very common. In every solid, the atoms or molecules
    are trapped in some position, and vibrate at some location, in some
    potential well. Close to the minimum of that potential well, the
    potential is harmonic, regardless of the nature of the potential. If
    we make a Taylor expansion up to second order, around the minimum of
    the well $x_0$:

    $$
        V(x_0+x) = V(x_0) + V'(x_0) x + \frac{1}{2} V''(x_0) x^2,
    $$

    then we can ignore the linear term in $x$, because $V'(x_0) = 0$ at the
    minimum, but $V''(x_0) \neq 0$, so that the potential is
    approximately harmonic (i.e. quadratic in $x$) close to its minimum,
    with \"spring constant\" $k = V''(x_0)$. So, in any solid at
    sufficiently low temperature, the equipartition theorem applies.

## The barometric height distribution

In this exercise you will derive the density of a gas in a gravitational
field (say, the atmosphere, or a dilute solution) as a function of
height. The gas behaves approximately as an ideal gas at a fixed
temperature $T$, number of particles $N$, and volume $V$.

1.  Calculate the probability $P(h)$ to find a particle at height $h$
    using the Boltzmann distribution.

2.  Calculate the density of particles $\rho(h)$ at height $h$, using
    $\rho(h) = \rho_0 P(h)$, with $\rho_0 = N/V$ the average density

3.  Find an expression for the length scale over which the density drops
    by a factor $e^{-1}\approx37\%$.

4.  What would this length scale be for oxygen molecules, if the
    temperature of the air were 0 $^\mathrm{o}$C? You can use the
    following numbers:

    -   Avogadro's number: $R_\mathrm{A}=6,022\cdot10^{23}$ (particles
        per mole)

    -   Boltzmann's constant: $k_\mathrm{B} = 1.38\cdot10^{-23}$ (J
        K$^{-1}$)

    -   Mass oxygen: 16u or 16 g per mole

5.  What would this length scale be for spherical gold nanoparticles
    with a radius of $5$ nm in an aqueous solution? The mass density of
    gold is approximately $19.3\cdot10^3$ kg/m$^3$ (19 kg per liter).

    The mass density of organic components is much lower than that of
    gold, so you can see that gravity is of no influence on a cellular
    scale.

## Open systems: association-dissociation equilibrium of a polymer, part II

A system that can exchange heat and particles with a reservoir is called
an "open system", or a "$\mu,V,T$-ensemble", or a "grand canonical
ensemble". The terms are used as synonyms, but shed light on specific
properties of these systems. As an example of an open system, one can
consider the electrolytes in a hydrogel in contact with a salt buffer,
or the electrolytes in a solution of proteins in contact with a buffer,
separated by a semi-permeable membrane. Open systems are called "open"
because particles can float in and out, they have a chemical potential
$\mu$ and temperature $T$ fixed by a reservoir (a "buffer"), and obey
specific statistical properties. The probability that an open system is
in a state $m$ is given by

$$
    P(m) = \frac{1}{\mathcal{Z}}e^{-\beta E_m + \beta \mu N_m}.
$$ (eq:Grand_canonical_distribution)

The expression looks similar to the Boltzmann distribution, equation
{eq}`eq:Boltzmann_distribution_set_5`, but with an extra term
$\beta \mu N_m$. It can be derived in a similar way as the Boltzmann
distribution. The chemical potential $\mu$ (the amount of energy needed
to add one particle to the system) is fixed by the reservoir, and
basically depends on the density of particles in the reservoir. The
number $N_m$ stands for the number of particles in the system, in state
$m$ (different states may have different numbers of particles, in
contrast to the $N,V,T$-ensemble). The factor $\mathcal{Z}$ is a
normalization factor, given by

$$
    \mathcal{Z} = \sum \limits_m e^{-\beta E_m + \beta \mu N_m}
$$ (eq:Grand_partition_function)

and is called the "grand canonical partition function". It seems an
inappropriately long name for a normalization factor, but it is secretly
much more than that. A few properties will be explored in this exercise.

1.  Show that the average number of particles in an open system can be
    derived from $\mathcal{Z}$ by

    $$
        \langle N \rangle = k_\mathrm{B}T \frac{\partial}{\partial \mu} \ln{\mathcal{Z}}
    $$

    Hint: work out the right hand side and see that it results in the
    definition of the expectation value.

    A certain polymer has $M$ sites where particles can bind. It is in
    contact with a solution (the buffer) with a chemical potential $\mu$
    and temperature $T$. The binding energy of a particle to the polymer
    is $\epsilon$, such that the energy of a configuration of $N$
    particles on the polymer is simply

    $$
        E = N\epsilon
    $$

    In equation {eq}`eq:Grand_partition_function` the sum is over all states.
    In the following questions, this sum will be rewritten as a sum over
    $N$, the number of particles in the system. For that, one needs to
    know how many states there are with $N$ particles.

2.  How many different states are there given that $N$ particles are
    bound to the polymer? Hint: in other words, in how many ways can
    $N$ identical particles bind to $M$ sites?

3.  Show that $\mathcal{Z}$ can be rewritten as

    $$
        \mathcal{Z} = \sum \limits_{N=0}^M \binom{M}{N} \left( e^{-\beta(\epsilon - \mu)} \right)^N
    $$

4.  Use the relation

    $$
        \sum \limits_{N=0}^{M} \binom{M}{N} a^N b^{M-N} = (a + b)^M
    $$

    to derive that

    $$
        \mathcal{Z} = (e^{-\beta(\epsilon-\mu)} + 1)^M
    $$

5.  Find the average number of particles that bind to the polymer
    $\langle N \rangle$, as a function of $\mu$ and sketch this
    function. Hint: when sketching it may be useful to check the
    limits of $\mu \rightarrow \infty$ and $\mu \rightarrow -\infty$ and
    $\mu = \epsilon$, and to check whether those limits make sense.
