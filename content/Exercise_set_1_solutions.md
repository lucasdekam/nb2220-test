# Problem set 1

## Problem 1.1
{ref}`Link to problem <sec:Oxygen_in_Box>`

1.  The probability density function is assumed to be constant, so
    $P(\mathbf{x}) = 1/V$, where $V$ is the volume of the classroom ($P$
    needs to be normalised). So, the probability of a single particle to
    be inside the box $p$ is

    $$
        p = \frac{V_\mathrm{box}}{V} = 0.001
    $$

    The probability that both are inside the box is therefore
    $p^2 = 1\cdot10^{-6}$, i.e. one in a million.

2. That probability would be, under the same assumptions as before,
    $P_\mathrm{in}\equiv p^N$ where $N$ is the number of particles, so

    $$
        P_\mathrm{in} \equiv p^N = \frac{1}{10^{3\cdot10^{25}}},
    $$

    that is, 1 divided by a 1 with $3\cdot 10^{25}$ zeroes.

3.  The total number of grains of sand on Earth and the total number of
    elementary particles in the Universe are completely negligible
    compared to this number.

4.  Given that the distribution randomises every hour, and that one
    would sample $M \equiv 10^{14}$ configurations, the probability that
    it would not occur is $(1-P_\mathrm{in})^M$. The probability to
    sample at least one situation where all the molecules are inside the
    box is

    $$    
        P_\mathrm{occur} = 1 - (1-P_\mathrm{in})^M \approx M P_\mathrm{in},
    $$

    which is still a fantastically small number, so there is no need to
    be afraid. (If you believe in the assumptions.)

5.  Even if $M$ were to be increased by a hundred orders of magnitude,
    it would still not be noticeable, except in the
    $(10^{25}-114)^\mathrm{th}$ significant digit.

6.  According to the above assumptions that probability would be

    $$
        P_\mathrm{in} = p^N = \frac{1}{10^{3000}},
    $$

    which is still
    unimaginably small. However, one needs to be careful with the
    assumption that the proteins be everywhere with equal probability.
    Proteins are constantly produced at certain locations in the cell,
    and they also interact with each other and the environment, changing
    the probability density distribution. To answer that, we need to
    know more about the Boltzmann distribution and other important
    concepts in Statistical Physics.

## Problem 1.2
{ref}`Link to problem <sec:Central_limit_theorem_dice>`

1.  The expectation value $\mu = 3.5$, and all outcomes are equally
    probable. The standard deviation is
    $\sigma = \sqrt{\langle x^2\rangle - \langle x \rangle^2} \approx 1.708$,
    $\sigma/\mu = 0.489$, and the distribution is constant,
    $P_n = \frac{1}{6}$, where $n$ is the outcome.

2.  The expectation value is $\mu_2 = 7$, the most probable outcome is
    $7$, and the distribution is triangular, peaked at 7

    $$
        P = \begin{cases}
                 a(n-1) & n\leq 7 \\
                 a(n-13) & n \geq 7
            \end{cases}
    $$

    with $a$ a normalisation constant. The
    standard deviation is close to $2.415$, $\sigma_2/\mu_2 = 0.345$.

3.  The expectation value is $\mu_3 = 10.5$, and the distribution
    consists of two parabolas, peaked at $n=10$ and $n=11$,

    $$
        P = \begin{cases}
                     a(n-2)^2 & n\leq 10 \\
                     a(n-19)^2 & n \geq 11
            \end{cases}
    $$

    with $a$ a normalisation constant. The
    standard deviation should be close to $\sqrt{3}\sigma \approx 2.96$,
    $\sigma_3/\mu_3 = 0.282$.

4.  One can use the central limit theorem here. The mean would be
    $100\mu$, and the standard deviation $10\sigma$,
    $\sigma_{100}/\mu_{100} = 0.049$, which is visible as a very narrow
    peak at $x = 350$.

5.  Similar as d) except that the distribution is extremely peaked at
    the mean. The mean is $\mu_N=N\mu_1 = 10^{12}\mu_1$ and the standard
    deviation is $\sigma_N=\sqrt{N}\sigma = 10^6\sigma$,
    $\sigma_N/\mu_N \approx 5\cdot 10^{-7}$, with $N=10^{12}$. The
    figure of this distribution cannot be distinguished from a delta
    distribution (which is zero everywhere, except at the mean), except
    if you would use a microscope and zoom in at the position of the
    mean.

## Problem 1.3
{ref}`Link to problem <sec:Orders_of_magnitude>`

These are estimates of the order of magnitude.

-   Taking the water molecule to be roughly 0.01 nm$^3$, and the cell to
    be $10 \mu \mathrm{m}^3$, would add up to $10^{12}$ molecules per
    cell, which is a number computer simulation algorithms cannot
    handle.

-   Taking the human body to be roughly 0.1 m$^3$ and a cell to be 10
    $\mu$m$^3$, and assuming the body to consist completely of densely
    packed cells, this would add up to $10^{16}$ cells. This is a slight
    overestimation, by about two orders of magnitude.

-   Taking a lipid membrane to be 10 $\mu$m$^2$ and a single lipid
    molecule to occupy 0.1 nm$^2$, this would add up to $10^8$ lipid
    molecules.

-   Taking the skin to be 1 m$^2$ and the cell to occupy 1 $\mu$m$^2$
    would add up to $10^{12}$ microbes, if the skin were densely packed
    with a monolayer of cells.

## Problem 1.4
{ref}`Link to problem <sec:Emergent_behavior>`

All phenomena can be seen as emergent. The final points would deserve a
much longer discussion, and have been discussed throughout the
centuries, around the globe. These short sketches add a nanobiological
flavor.

1.  Temperature from the motion of molecules

2.  Brownian motion from the collisions with other particles

3.  The elasticity of a cell membrane from the interactions between the
    molecules in the membrane and the average kinetic energy of the
    molecules (their temperature)

4.  Cell division from multiple processes including protein interaction
    networks that regulate the binding of filamentous proteins that
    shape and contract the cell at the right location. Underneath is
    still the mechanics of all the molecules, having very specific
    interactions. The expression of genes into proteins should also be
    distinguished.

5.  Thoughts could be (speculatively) the consequence of a specific
    firing pattern of neurons, coupled to sensorial patterns and
    physical stimuli, which relate to the functioning of the individual
    cells involved, their components and their molecules. Many
    layers\...

6.  Music as emerging from individual notes, or a delicate superposition
    and succession of sounds, coupling to thoughts and internal
    processes via aural stimuli.

7.  Awareness could be a collection of thoughts and other neuronal
    patterns, coupled to the physical infrastructure and environment,
    and seems difficult to define.
