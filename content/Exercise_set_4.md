(ch:chapter4)=
# Boltzmann statistics and entropy

(sec:Stirling_approximation)=
## Stirling approximation

Counting the number of microstates is an essential procedure in
statistical physics. These numbers are usually very large, and often
appear as factorial numbers $N!$ with $N$ a very large number. Common
calculators typically do not go beyond $100!$. Fortunately, it is often
sufficient to calculate the logarithm of that number, $\ln{N!}$. The
Stirling approximation is then very useful:

$$
  \ln{N!} \approx N \ln{N} - N + \frac{1}{2}\ln{(2\pi N)}.
$$

The last
term is completely negligible for large $N$. The first two terms can be
derived quickly. Given that

$$
  \ln{N!} = \ln{(N\cdot(N-1)\cdot...1)} = \ln{N} + \ln{(N-1)} + ... + \ln{1} = \sum \limits_{n=1}^N \ln{n},
$$

one can approximate the sum by an integral

$$
  \int \limits_1^N \ln{(x)} \ dx = N \ln{N} - N + 1.
$$

For large $N$ one
can ignore the $+1$ term, and obtain the extremely useful result, which
we will refer to as the Stirling approximation:

$$
\boxed{\ln{N!}\approx N\ln{N} - N}
$$ (eq:Stirling)

1.  What is the relative error of the Stirling approximation for
    $\ln{100!}$? If your calculator cannot handle $100!$ you can pick a
    smaller number.

    Macroscopic systems typically contain $>10^{20}$ particles, and in
    that case the approximation is as good as exact.

2.  Use the Stirling approximation to rewrite $\ln{\binom{N}{n}}$.

3.  Find the value of $n$ that maximises $f(n) = \ln{\binom{N}{n}}$.

4.  Find the value of $n$ that maximises
    $f(n) = \ln{\binom{N}{n}} + n \epsilon$.

(sec:Second_law_via_Boltzmann)=
## Second law of thermodynamics

In this exercise you are going to derive the second law of
thermodynamics from the definition of the Boltzmann entropy

$$  
  \boxed{S=k_\mathrm{B} \ln{\Omega}}
$$ (eq:Boltzmann_entropy)

and the definition of temperature

$$
    \boxed{\frac{\partial S}{\partial E} = \frac{1}{T}}
$$ (eq:Temperature)

In the future,
we will call the Boltzmann entropy just "the entropy", but know that
there are very similar expressions defined for probability distributions
(Gibbs entropy), quantum systems (Neumann entropy) and information
theory (Shannon entropy). All these definitions of entropy can be
related back to the Boltzmann entropy, and have similar, if not
identical properties. The definition of temperature may seem a bit
awkward at first, but you will see that it is very meaningful in the
end.

1.  Two isolated systems, system 1 and system 2, have entropy $S_1$ and
    $S_2$, and energy $E_1$ and $E_2$, respectively. System 1 has a
    total number of $\Omega_1(E_1)$ microstates with energy $E_1$, and
    system 2 has $\Omega_2(E_2)$ microstates with energy $E_2$. Show
    that entropy is extensive.

2.  The two systems are now linked together with a thin wall in between,
    which allows for heat transfer. The systems together are still
    isolated from the environment. Explain that the total number of
    possible configurations of the combined system is now

    $$
      \Omega_\mathrm{tot} = \sum \limits_{E_1} e^{\frac{S_1(E_1)}{k_\mathrm{B}} + \frac{S_2(E-E_1)}{k_\mathrm{B}}}
    $$ (eq:total_number_of_configurations)

    and demonstrate that the total entropy should increase, or stay the
    same, when the systems are connected.

    Under special conditions, the entropy will stay constant. These
    conditions will be derived in the following questions.

3.  The number of configurations depends exponentially on the entropy,
    $\Omega = \exp{\left(\frac{S}{k_\mathrm{B}}\right)}$, where $S$ is
    already a large number, typically (much) larger than the number of
    particles $N$. Argue that the sum in equation {eq}`eq:total_number_of_configurations`
    is completely
    dominated by its maximum, and that all the other terms can be
    ignored.

4.  Demonstrate that the condition for this maximal value is

    $$
      \frac{\partial S_1 (E_1)}{\partial E_1}  = \frac{S_2(E_2)}{\partial E_2}.
    $$ (eq:thermal_equilibrium_entropy)

    Call the energy of system 1 for which $S_1 + S_2$ is maximal $E^*$.

5.  If one would prepare system 1 with an initial energy $E^*$, nothing
    would change after the connection with system 2. No energy would
    flow between the systems and the total entropy would remain the
    same. In that case, the systems are said to be in thermal
    equilibrium. So the equation {eq}`eq:thermal_equilibrium_entropy` you derived in the previous question, is a condition for
    thermodynamic equilibrium. Derive the condition for thermal
    equilibrium in terms of $T_1$ and $T_2$.

6.  If we prepare system 1 at a higher temperature than system 2,
    $T_1>T_2$ before they are connected, the entropy would necessarily
    increase (you already derived this). For small changes

    $$
      \delta S = \frac{\partial S_1}{\partial E_1} \delta E_1 + \frac{\partial S_2}{\partial E_2}\delta E_2.
    $$

    Show that the change in energy $\delta E_1 < 0$.

7.  Argue that you just derived the second law of thermodynamics.

(sec:Canonical_ensemble)=
## The microcanonical ensemble and the canonical ensemble

A fundamental assumption in statistical physics is that

> In a closed system, each microstate is equally probable.

<!-- Isolated system? Closed and isolated are sometimes used interchangably,
but in chemistry they're different. -->

We refer to such a system as a *microcanonical ensemble*. So, in the
microcanonical ensemble all configurations with energy $E$ are equally
probable with probability

$$
  P(n) = \frac{1}{\Omega(E)},
$$

where
$\Omega(E)$ is the total number of configurations with energy $E$, and
each microstate is labelled by an index $n$ (in general, one can label
microstates in different ways, but let's assume we can count them with
this index $n$).

We can now derive a probability distribution for systems in contact with
a thermal reservoir, as shown in {numref}`canonical_ensemble`, which we call the
*canonical ensemble*. The system and reservoir together are isolated from the
environment, so together they form a microcanonical ensemble. Each
microstate of the entire system is equally probable, but not in the
system and reservoir separately, because each microstate of the system
constrains the number of possible microstates of the reservoir. In this
exercise you will derive the probability distribution $P(n)$ for each
state $n$ in the system.

```{figure} images/canonicalensemble.svg
---
name: canonical_ensemble
width: 40%
---
The canonical ensemble: a system in thermal contact with a
reservoir.
```

1.  The total number of microstates of the entire system is

    $$
      \Omega_\mathrm{tot}(E) = \sum \limits_n \Omega_\mathrm{Reservoir}(E-E_n)
    $$

    where $n$ labels all possible microstates of the system. So, for
    each microstate $n$ of the system, the reservoir can be in
    $\Omega(E-E_n)$ different microstates. Express
    $\Omega_\mathrm{Reservoir}$ in terms of the entropy of the
    reservoir, and make a Taylor expansion around $E$ up to first order.

2.  Use the definition for temperature (equation {eq}`eq:Temperature`) and use clear
    argumentation to derive

    $$
      \boxed{P(n) = \frac{1}{Z} e^{-\frac{E_n}{k_\mathrm{B} T}}}
    $$ (eq:Canonical_ensemble_P)

    with normalisation factor

    $$
      \boxed{Z = \sum \limits_n e^{-\frac{E_n}{k_\mathrm{B} T}}}
    $$ (eq:Partition_function)

    Equation {eq}`eq:Canonical_ensemble_P` is called the
    *Boltzmann distribution*, and equation
    {eq}`eq:Partition_function` is called the *partition
    function*. If you managed to solve this exercise, you just derived
    the most important equations of this course.

(sec:Random_walk_part_II)=
## Random walk, part II

<!-- I'm pretty sure something like this is studied in Biophysics
and Computational Science as well. Possibly relate it somehow? -->

Einstein used the "random walk" to describe diffusing particles. The
experiments of Jean Perrin confirmed that particles in solution actually
make a random walk. The random walk can also be used to describe
flexible polymers. Let's consider a polymer consisting of $N$ identical
monomers. Each monomer is modeled as a rigid segment with length $b$,
and each segment is connected to the next in such a way that they can
rotate freely with respect to each other. For simplicity, we will ignore
all possible interactions between the monomers, and refer to this
polymer as an "ideal polymer" (analogous to a gas of non-interacting
particles, the "ideal gas"). Therefore, each possible configuration of
the polymer has the same energy, and according to the previous
exercises, is equally probable. In this exercise we are going to
calculate the amount of work that is needed to stretch this polymer over
a distance $R$, or more precisely, the work required to increase the
end-to-end distance from $0$ to $R$. First we will calculate the
probability that the end-to-end distance is $R$; given that each
configuration is equally likely,

$$
  P(R) = \frac{\Omega(R)}{\Omega_\mathrm{tot}}.
$$ (eq:probability_R)

Counting all the
possible configurations with an end-to-end distance $R$ can be done in
the following way. A random configuration is sampled by a set of $N$
random vectors $\vec{r}_i$ of length $b$ for each segment $i$. The
vector pointing from the beginning of the polymer to the endpoint is
then given by $\vec{R} \equiv \vec{r}_1+\vec{r}_2+...+\vec{r}_N$, see
{numref}`Flexible_polymer`.

```{figure} images/flexiblepolymer.svg
---
name: Flexible_polymer
width: 50%
---
A configuration of a flexible polymer, describing a random walk in
3 dimensions.
```

1.  Determine the mean of $\vec{r}_1$ by simple arguments. Hint: Write
    down the mathematical expression for the mean, and remember that
    each configuration is equally probable.

2.  If we write the vector $\vec{r}_1$ in terms of Cartesian coordinates
    $\vec{r}_1 = (x_1,y_1,z_1)$, argue that
    $\langle x_1^2 \rangle = \frac{1}{3}b^2$. (Hint: work out
    $\langle \vec{r}_1 \cdot \vec{r}_1 \rangle$ and remember that the
    vector can point in each direction with equal probability.)

3.  Give the standard deviation of the $x$-component of
    $\vec{R}=(x,y,z)$. (Hint: $x = x_1 + x_2 + ... x_N$ and use that
    $N$ is large.)

4.  What is the probability to find the endpoint at $\vec{R}=(x,y,z)$?
    (Hint: calculate $P(x)$ first - the probability that the
    $x$-component of $\vec{R}$ is at position $x$, and then use that
    $P(x,y,z)=P(x)P(y)P(z)$.)

5.  How does the entropy scale with $R$, which is the length of $\vec{R}$? (Hint:
    Remember that $S(R)$ depends on $\Omega(R)$, the number of
    configurations for a fixed end-to-end distance $R$, and that
    $\Omega(R)$ is related to $P(R)$ by equation {eq}`eq:probability_R`.)

6.  Now the polymer is coupled to a thermal reservoir, by putting it
    into an aqueous solution. How does the free energy $F = E - TS$
    depend on the distance between the endpoints $R$? Does the answer
    look familiar to an important system in classical mechanics?

7.  Flexible polymers are sometimes referred to as *entropic springs*.
    Now you know the origin. They have elastic properties, depending on
    the number of segments $N$, the segment length $b$, and to some
    extent on the temperature $T$. Give the spring constant of a
    polymer, depending on $N,b$ and $T$.

8.  How much work do you have to perform to stretch the polymer from
    $R=0$ to $R = \sqrt{N} b$? And to $R = 2 \sqrt{N} b$?

The energy value $k_\mathrm{B}T$ is very meaningful in thermodynamic
systems, as we will see shortly. (It is comparable to the typical
kinetic energy of the particles.)
