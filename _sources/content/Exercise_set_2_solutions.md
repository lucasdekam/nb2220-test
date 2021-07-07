# Problem set 2

## Problem 2.1

There were very good suggestions and ideas during the work session. Some
systems fall into multiple categories, depending on circumstances, and
there may be other ways to classify them beyond the options that were
mentioned. Here are some suggestions. Your arguments are more important
than the actual answer.

1.  Yogurt: can be liquid, can be gel, can be called solid

2.  Diamond: (famous symmetry of a) crystal

3.  The salt ions in vegetable soup: gas (a pinch of salt), liquid (a
    spoon), solid (a cup), a *plasma* (fluid of charged particles - are
    also abundant in outer space, or in fusion reactors, but also in
    vegetable soup)

4.  a school of sardines: nematic liquid crystal, liquid, a 'swirlonic
    state' (yes). One person mentioned gel, and that seemed unexpectedly
    appropriate. These schools seem to behave visco-elastically when
    perturbed by predators.

5.  actin networks: (active) gel, solid / glass when dry

6.  a cell membrane: liquid with more solid-like rafts

7.  a sample of proteins after Cryo-EM: glass, random aggregate

8.  skin tissue: gel / solid / \...

9.  a soap bubble: generally liquid. May form foams.

10. muscle tissue: solid, active gel, fiber composite, \...

## Problem 2.2

\...

## Problem 2.3

1.  See notes: $\mu = 0$, $\sigma = 1$.

2.  The mean $\mu_N = N \mu = 0$ (it should be zero, because this random
    walk is symmetric - walking left or right is equally probable). The
    standard deviation $\sigma_N = \sqrt{N}\sigma = 10$

3.  After $N=10^4$ steps, $\sigma_N = \sqrt{N}\sigma = 100$. The random
    walk describes diffusion, and this process is not efficient to
    explore space. The distance that one typically explores ($\sigma_N$)
    is not linear with the number of steps, but is proportional with
    $\sqrt{N}$. To give a feeling, if 1 step is 1 m and takes 1 s, then
    it would take 100 s to explore 10 m, $10^4$ s to explore 100 m
    (about 3 hours), and $10^6$ s to explore 1 km (about half a month).
    Check how long it takes to explore 10 km or 100 km\... This can be a
    serious issue if you want particles to diffuse to a template, or to
    diffuse over a large distance.

4.  If one ends up $y$ steps to the right, we are interested in all
    combinations of steps that lead to $y$ after $N$ steps, so
    $X_1+X_2+...+X_N=Y$, where all the stochastic variables $X$ can take
    values -1 (step to the left) or 1 (step to the right). This is very
    similar to the problem with the dice, except that we only have 2
    possible outcomes here instead of 6. We can use the central limit
    theorem here to argue that

    $$P(y) = C e^{-\frac{y^2}{2N}}$$

    with $C$
    a normalisation constant.

5.  In this case one can also calculate the exact answer. Given that one
    ends up at position $y$ after $N_+$ steps to the right and $N_-$
    steps to the left, with a total number of $N$ steps, we can figure
    out how many steps one has to take to the right:

    $$\begin{aligned}
            N_+ - N_- &= y\\
            N_+ + N_- &= N
    \end{aligned}$$

    so

    $$\begin{aligned}
            N_+ &= \frac{N+y}{2}\\
            N_- &= \frac{N-y}{2}
    \end{aligned}$$

    so the total number of ways in which one can
    walk to $y$ is $\binom{N}{N_+} = \binom{N}{N_-}$. The total number
    of random walks is $2^N$ (for each step there are 2 possibilities),
    so the probability that one would end up at $y$ after $N$ steps is

    $$
        P(y) = 2^{-N}\binom{N}{\frac{N+y}{2}} = 2^{-N}\frac{N!}{\left(\frac{N+y}{2}\right)!\left(\frac{N-y}{2}\right)!}
    $$

In the next sessions we will see what these results imply for the shape
of flexible polymers, and for association-dissociation equilibria.

## Problem 2.4

A long polymer has $N$ sites where certain types of particles can bind.
These particles can bind to each site with equal probability. If a
particle is bound to a site, no other particle can bind to that site.

1.  There are $N$ different sites, so one particle can bind in $N$ ways.

2.  The first particle in $N$ ways, the second in $N-1$ ways, and the
    $n^\mathrm{th}$ in $N-n+1$ ways, so the total number is

    $$\frac{N!}{(N-n)!}$$

3.  If the particles are all identical, we can swap particles without
    changing the configuration, so the total number of ways is

    $$\binom{N}{n}$$

4.  It is a binomial distribution, so the largest value is obtained for
    $n=\frac{N}{2}$ (by knowledge of what a binomial distribution
    typically looks like, or by observing that the binomial distribution
    has a symmetry around $n=\frac{N}{2}$ and is increasing with
    $n<\frac{N}{2}$), or via the Stirling approximation and seeking the
    extremum - see next session.)

5.  One would get a binomial distribution, which looks very much like a
    Gaussian distribution for $N=100$ (see previous exercise), with a
    mean of $\mu_N=50$.

6.  In fact, one can map this situation on a random walk. Introducing
    $X_1+X_2+...X_N=Y$, where each $X_i$ can take the value 0 (no
    particle at site $i$) or 1 (a particle bound at site $i$) with equal
    probability, the mean $\mu_N=50$ and standard deviation
    $\sigma_N=5$. The number of ways would be proportional to this
    distribution ($2^N P(n)$).

7.  Bonus challenge (optional): The solutions are now: a) $N$, b)
    $N^n$, c) $\binom{N+n-1}{n}$. If you were able to solve f) please
    contact me.

    These results will be used again in the future. They are very
    meaningful if one is interested in the elastic properties of
    polymers, or the number of occupied binding sites on a polymer or
    membrane.
