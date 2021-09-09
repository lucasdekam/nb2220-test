# Problem set 4

## Problem 4.1

1.  Without the $\frac{1}{2}\ln{(2\pi N)}$ term, the relative error is
    less than 1 percent. With that term, it is very small $<10^{-5}$.

2.  $$\begin{aligned}
            \ln{\binom{N}{n}} &= \ln{\frac{N!}{n!(N-n)!}} = \ln{N!} - \ln{n!} - \ln{(N-n)!}\\
            &= N\ln{N} - N - n\ln{n} + n - (N-n)\ln{(N-n)} + (N-n)\\
            &= N\ln{N} - n\ln{n} - (N-n)\ln{(N-n)}
    \end{aligned}$$

3.  $$\begin{aligned}
            \frac{df}{dn} &= 0\\
            &= - \ln{n} + 1 + \ln{(N-n) - 1}\\
            &= \ln{\frac{N-n}{n}}
    \end{aligned}$$

    Taking the exponent one finds the value of $n$
    that maximises $f$

    $$\begin{aligned}
            \frac{N-n}{n} &= e^0 = 1\\
            n &= \frac{N}{2}
    \end{aligned}$$

    We now proved that the maximum of a binomial
    function is at $n = \frac{N}{2}$. Nothing new perhaps, but the next
    question is more difficult.

4.  $$\begin{aligned}
            \frac{df}{dn} &= 0\\
            &= - \ln{n} + 1 + \ln{(N-n) - 1} + \epsilon\\
            &= \ln{\frac{N-n}{n} + \epsilon}
    \end{aligned}$$

    Taking the exponent one finds the value of $n$
    that maximises $f$

    $$\begin{aligned}
            \frac{N-n}{n} &= e^\epsilon\\
            n &= \frac{N}{1+e^\epsilon}
    \end{aligned}$$ (eq:Langmuir_isotherm)

    Although these questions meant as a purely
    mathematical exercise to practice with the Stirling approximation,
    equation {eq}`eq:Langmuir_isotherm` will often reappear in statistical
    physics (although perhaps with different symbols in the exponent,
    instead of $\epsilon$). It describes for example how electrons
    distribute over the energy levels in a metal, which determines the
    specific heat and conductivity of the material (say, how much energy
    it costs to heat up a cast iron pan, or how easy it is to put a
    current through it). In this case, the distribution is known as the
    *Fermi-Dirac distribution*. It also describes how many ionisable
    groups on a polymer or protein dissociate in a certain solution. It
    that case, the distribution is known as the *Langmuir isotherm*,
    named after Irvin Langmuir. This will be explained in more detail in
    the next chapter.

## Problem 4.2

1.  $$\begin{aligned}
            S_\mathrm{tot}(E) &= k_\mathrm{B}\ln{\Omega_\mathrm{tot}(E)}\\
            &= k_\mathrm{B}\ln{\Omega_1(E_1)\Omega_2(E_2)}\\
            &= k_\mathrm{B}\ln{\Omega_1(E_1)}+k_\mathrm{B}\ln{\Omega_2(E_2)}\\
            &= S_1(E_1) + S_2(E_2)
    \end{aligned}$$

2.  Before the systems are connected, the total number of different
    microstates is

    $$\Omega_\mathrm{tot}(E) = \Omega_1 (E_1)\Omega_2(E-E_1)$$

    This number of states is still accessible after the systems are
    connected, but now, energy can be distributed leading to even more
    microstates,

    $$\Omega_\mathrm{tot} = \sum \limits_{E_1} \Omega_1 (E_1)\Omega_2(E-E_1) = \sum \limits_{E_1} e^{\frac{S_1(E_1)}{k_\mathrm{B}} + \frac{S_2(E-E_1)}{k_\mathrm{B}}}$$

    so the total entropy will increase or stay constant:

    $$\begin{aligned}
            S_\mathrm{tot}(E) &= \ln{\left(\sum \limits_{E_1} \Omega_1 (E_1)\Omega_2(E-E_1)\right)}\\
            &\geq& \ln{\Omega_1 (E_1^{(\mathrm{i})})\Omega_2(E-E_1^{(\mathrm{i})})}\\
            &= S_1(E_1^{(\mathrm{i})}) + S_2(E-E_1^{(\mathrm{i})})
    \end{aligned}$$

    with $E_1^{(\mathrm{i})}$ the initial energy of
    system 1. The initial energy $E_1^{(\mathrm{i})}$ is only one of the
    values in the summation, so it seems as if the entropy would always
    increase. However, the answers below will show that the sum is
    completely dominated by one term.

3.  The entropy $S$ is a very large number, and therefore the maximum
    value of $\exp{\frac{S}{k_\mathrm{B}}}$ will dominate all other
    terms. For example, if one compares $N+10$ with $N$, the factor 10
    may seem negligible, but if these numbers are in an exponent, then
    the first term is $e^{10}$ times larger than the second.

4.  At the maximum value of $S_1+S_2$, the derivative with respect to
    $E_1$ is zero,

    $$\frac{\partial}{\partial E_1} (S_1(E_1) + S_2(E-E_1)) = 0$$

    so (remembering $E_2 = E - E_1$)

    $$
        \frac{\partial S_1 (E_1)}{\partial E_1}  + \frac{\partial S_2(E_2)}{\partial E_2}\frac{\partial E_2}{\partial E_1} = 0
    $$

    leads to

    $$
        \frac{\partial S_1 (E_1)}{\partial E_1}  = \frac{S_2(E_2)}{\partial E_2}
    $$ (eq:thermal_equilibrium_entropy_sols)

    The energy $E_1$ for which this condition is met will be written as
    $E^*$. If system 1 is prepared with this energy, and system 2 with
    energy $E_2 = E-E^*$, then nothing would change after the systems
    are connected. Equation {eq}`eq:thermal_equilibrium_entropy_sols` is the condition for
    thermodynamic equilibrium.

5.  With the definition of temperature

    $$\frac{\partial S}{\partial E} = \frac{1}{T}$$

    this leads quickly
    to the statement, that in thermodynamic equilibrium

    $$T_1=T_2$$

6.  For small changes

    $$\delta S = \frac{\partial S_1}{\partial E_1} \delta E_1 + \frac{\partial S_2}{\partial E_2}\delta E_2.$$

    Since $\delta S>0$ and $\delta E_1 = - \delta E_2$, one finds that

    $$\delta S = \left(\frac{1}{T_1}  - \frac{1}{T_2}\right)\delta E_1.$$

    So if $T_1>T_2$ then $E_1$ has to be smaller than zero,
    $\delta E_1 < 0$.

7.  The previous question demonstrates that energy flows from high to
    low temperature, and not the other way around (without external
    influence). This is the second law of thermodynamics.

## Problem 4.3

1.  The total number of microstates of the entire system is

    $$\Omega_\mathrm{tot}(E) = \sum \limits_n \Omega_\mathrm{Reservoir}(E-E_n)$$

    where $n$ labels all possible microstates of the system. So, for
    each microstate $n$ of the system, the reservoir can be in
    $\Omega(E-E_n)$ different microstates. Express
    $\Omega_\mathrm{Reservoir}$ in terms of the entropy of the
    reservoir, and make a Taylor expansion around $E$ up to first order.

    $$\begin{aligned}
            \Omega_\mathrm{tot}(E) &= \sum \limits_n \Omega_\mathrm{R}(E-E_n)\\
            &= \sum \limits_n e^{\frac{1}{k_\mathrm{B}}S_\mathrm{R}(E-E_n)}
    \end{aligned}$$

    A Taylor expansion of $S_\mathrm{R}$ leads to

    $$\begin{aligned}
            S_\mathrm{R}(E-E_n) = S_\mathrm{R}(E) + \frac{\partial S_\mathrm{R}}{\partial E}(-E_n) + ...
    \end{aligned}$$

    And using the definition of temperature

    $$\frac{\partial S_\mathrm{R}}{\partial E} = \frac{1}{T}$$

    with $T$
    the temperature of the reservoir. So up to first order in $E_n$ one
    finds

    $$\begin{aligned}
            S_\mathrm{R}(E-E_n) = S_\mathrm{R}(E) - \frac{E_n}{T}
    \end{aligned}$$

2.  For a given state $n$ the total number of configurations is

    $$\begin{aligned}
            \Omega_\mathrm{R}(E-E_n) &= e^{\frac{1}{k_\mathrm{B}} S_\mathrm{R}(E-E_n) }\\
            &= e^{\frac{1}{k_\mathrm{B}}S_\mathrm{R}(E)} e^{-\frac{E_n}{k_\mathrm{B}T} }\\
            &= c e^{-\frac{E_n}{k_\mathrm{B}T} }
    \end{aligned}$$

    So the probability that the system is in state
    $n$, is

    $$\begin{aligned}
            P(n) &= \frac{\Omega_\mathrm{R}(E-E_n)}{\Omega(E)}\\
            &=\frac{1}{Z} e^{-\frac{E_n}{k_\mathrm{B} T}}
    \end{aligned}$$

    known as the Boltzmann distribution, with normalisation factor

    $$Z = \sum \limits_n e^{-\frac{E_n}{k_\mathrm{B} T}}$$

    known as the partition function. These equations play a central role in
    statistical physics.

## Problem 4.4

1.  The mean $\langle \vec{X}_1 \rangle$ should be zero, because each
    vector is equally probable as the vector pointing in the opposite
    direction, so the expectation value should add up to zero. In more
    mathematical language

    $$\mu = \langle \vec{r}_1 \rangle = \int \vec{r}_1 P(\vec{r}_1) d\vec{r}_1$$

    Officially one should integrate over all vectors $\vec{r}_1$ with
    length $b$, but it saves some effort to observe that
    $P(\vec{r}_1) = P(-\vec{r}_1)$, so that all terms will cancel. One
    can also observe that $P$ has the same value for each $\vec{r}$,
    such that it can be taken out of the integral. What is left is a
    3-dimensional integral with symmetric bounds over odd functions
    (e.g. $\int x dx = 0$).

2.  $$\begin{aligned}
            \langle \vec{r}_1 \cdot \vec{r}_1 \rangle &= \langle b^2 \rangle = b^2\\ &= \langle x_1^2 + y_1^2 + z_1^2 \rangle\\
            &= \langle x_1^2 \rangle + \langle y_1^2 \rangle + \langle z_1^2 \rangle
    \end{aligned}$$

    The next crucial observation is that
    $\langle x_1^2 \rangle = \langle y_1^2 \rangle = \langle z_1^2 \rangle$,
    because all vectors are equally probable (so there should be no
    preference for the $x,y$ or $z$-direction). It follows then that
    $\langle x_1^2 \rangle= \frac{1}{3}b^2$ as requested.

3.  From the previous questions we can calculate the mean of $x_1$ to be
    $\mu = 0$ and the standard deviation of $x_1$ to be
    $\sigma = \frac{1}{\sqrt{3}}b$. Using the central limit theorem, we
    know now that the mean of $x$ is $\mu_N = 0$ and the standard
    deviation $\sigma_N = \sqrt{\frac{N}{3}}b$

4.  Again, using the central limit theorem, the probability to find the
    $x$-component of $\vec{R}$ at position $x$ should be

    $$P(x) = c e^{-\frac{3x^2}{2Nb^2}}$$

    with $c$ some normalisation
    constant (not too important now). Similarly for the other two
    components $y$ and $z$. Therefore,

    $$P(x,y,z) = P(x)P(y)P(z) = c^3 e^{-\frac{3\left(x^2+y^2+z^2\right)}{2Nb^2}} = c^3 e^{-\frac{3R^2}{2Nb^2}} = P(R)$$

5.  The entropy depends on the number of configurations $\Omega(R)$, and
    $\Omega(R)$ is proportional to the probability $P(r)$, because

    $$P(R) = \frac{\Omega(R)}{\Omega_\mathrm{tot}}$$

    that is, the number
    of configurations for a fixed end-to-end distance $R$, divided by
    the total number of configurations. The entropy as a function of $R$
    is therefore

    $$S(R) = k_\mathrm{B} \ln{\Omega} = -\frac{3k_\mathrm{B}R^2}{2Nb^2} + C$$

    with $C$ some term not depending on $R$.

6.  The energy does not depend on the configuration of the polymer (it
    is an ideal polymer) so $E$ is independent of $R$, so

    $$F = E-TS = \frac{3}{2}\frac{k_\mathrm{B}T}{Nb^2}R^2 = \frac{1}{2}kR^2$$

    which is the equation for a Hookean spring. Terms that do not depend
    on $R$ are ignored, making use of the property that one can ignore
    constant terms in a potential. (This is because potentials cannot
    be measured directly, only potential differences or the derivative,
    such that constant terms can be ignored (with some care).)

7.  Ideal polymers behave as perfect springs, with spring constant

    $$k = \frac{3k_\mathrm{B}T}{Nb^2}$$

    Long, flexible, neutral polymers
    tend to behave as ideal polymers. Also, polymers in dense \"melts\"
    behave like ideal polymers, and even stiff polymers effectively do,
    as long as they are much longer than their \"persistence length\".
    So, in this exercise you derived a property that is applicable to a
    large class of polymers.

8.  The work required to pull the end of the polymer from $R=0$ to
    $R = \sqrt{N}b$ is $\frac{3}{2}k_\mathrm{B}T$, and to
    $R = 2\sqrt{N}b$ it is $6 k_\mathrm{B}T$. The typical kinetic energy
    of the components in a system in thermal equilibrium is
    $\frac{3}{2}k_\mathrm{B}T$ (will be derived in set 5), and potential
    barriers that are smaller than this value can be easily crossed.
    Barriers with a higher value can only be crossed by rare
    fluctuations, or by external force. The size of a flexible polymer
    is usually expressed as
    $\sqrt{\langle R^2 \rangle} = \sqrt{\langle x^2 \rangle + \langle y^2 \rangle + \langle z^2 \rangle} = \sqrt{N}b^2$
    (the *radius of gyration*).
