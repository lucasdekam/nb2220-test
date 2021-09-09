(sec:chapter3)=
# Classical thermodynamics

(sec:Thermodynamic_potentials)=
## Thermodynamic potentials

The first law of thermodynamics states that:

> The amount of work required to change an isolated system from state 1 to
state 2 is independent of how the work is performed.

In other systems, there may also be heat exchange with the environment,
or particle exchange. Properties of a given state are called a
*functions of state*. The energy $E$ is a function of state, and so are
$p, T$ and $V$. Heat $Q$ and work $W$ are not functions of state,
because they represent energy transfer during a transition from state 1
to state 2, and depend on the path taken from 1 to 2. External processes
can change the energy $E$ of the system, and an infinitesimal change is
described by

$$
  \mathrm{d}E = T\mathrm{d}S - p\mathrm{d}V + \mu \mathrm{d}N.
$$ (eq:firstlaw)

The Helmholtz free energy $F$ can be obtained via a *Legendre transform*:

$$
\begin{aligned}
    F(T,V,N) &= E(S,V,N) - \frac{\partial E}{\partial S} S \\
    &= E - TS.
\end{aligned}
$$ (eq:Helmholtz)

As you can see, the Helmholtz free energy
is written as a function of $T$ whereas the energy is written as a
function of $S$. With similar Legendre transforms one can replace $V$
with $p$, or $N$ with $\mu$. The new functions that one obtains are
called *thermodynamic potentials*. These potentials contain useful
information about different systems: $E(S,V,N)$ about isolated systems,
$F(T,V,N)$ about systems in contact with a thermal reservoir, $G(T,p,N)$
about systems in contact with a thermal reservoir and at constant
pressure, $\Phi(T,V,\mu)$ about systems in contact with a thermal
reservoir and particle reservoir.

:::{admonition} The Legendre transform
:class: tip, dropdown
Similar to a Fourier transform or a Laplace transform, the Legendre transform
is a way to display information in a different way that might be more useful
in a certain context. The Legendre transform of a
function $f(x)$ is used when it is easier to think about or control the
*derivative* of $f$ with respect to $x$, than $x$ itself. Mathematically,
the Legendre transform of $f$ is given by

$$
  g(u) = ux - f(x),
$$ (eq:legendre_def)

with $u = \mathrm{d}f/\mathrm{d}x$.

For a system in contact with a thermal reservoir, $T = \partial E/\partial S$
is easier to think about than the entropy $S$. The temperature is
constant and easy to measure or control, whereas the entropy may depend on the
temperature in some complicated manner. So, let's take the Legendre transform
of $E(S)$ to get a function of $T$. According to equation {eq}`eq:legendre_def`,
the Legendre transform is given by

$$
  TS - E(S),
$$

which is $-F(T)$, according to equation {eq}`eq:Helmholtz`. We define
$F(T)$ as the *negative* of the Legendre transform to give it the same sign
as the internal energy $E$. The same thing is true for other thermodynamic
potentials.

The Helmholtz free energy $F(T)$ contains information about the energy in
terms of the temperature. It is called 'free energy' because it represents
the amount of work you can extract from a system that is being kept at a
constant temperature (apparently, there is an energy $TS$ that
you cannot extract as work).

So far we considered exchanging $S$ with $T$ for a system
in contact with a thermal reservoir. If your system is in direct contact with
the atmosphere, the pressure is just the atmospheric pressure (in equilibrium),
and the volume may change. Hence, you might consider exchanging $V$ with
$p= -\partial E/\partial V$ using a Legendre transform. Similarly, if your
system can exchange particles with its environment, it's often easier to consider
the chemical potential $\mu = \partial E/ \partial N$ than $N$.

If you want to know more about Legendre transforms, [this](https://www.lpsm.paris/pageperso/lecomte/references2013/making-sense-of-legendre-transform.pdf) article is a good place to start {cite:p}`zia2009making`.
:::

```{figure} images/foursystems.svg
---
name: thermodynamic_systems
width: 100%
---
Find the appropriate thermodynamic potential for these four systems.
```

1.  Find the appropriate thermodynamic potential for the
    systems in {numref}`thermodynamic_systems`. (Hint: check which variables
    in the system are constant. One of the systems is not mentioned
    above, but try to figure out what variables this potential should
    depend on.)

2.  Give the differential form of $F$, that is, $\mathrm{d}F = ...$ (Hint: use
    the product rule for forms: $\mathrm{d}(xy)= y \mathrm{d}x + x \mathrm{d}y$.)

3.  Derive the Grand potential $\Phi(\mu,V,T)$ from the Helmholtz free
    energy, by means of a Legendre transformation.

4.  Derive the Gibbs free energy from the Helmholtz free energy, by
    means of a Legendre transformation. What thermodynamic variables
    does it depend on, and what thermodynamic process does it naturally
    describe?

5.  Argue that $G$ can be written as $G = \mu(p,T) N$. (Hint: check
    whether variables are extensive or intensive.)

When physicists talk about "free energy" they usually mean the
Helmholtz free energy $F$, and when chemists talk about free energy,
they usually mean the Gibbs free energy $G$.

(sec:thermodynamic_variables)=
## Thermodynamic variables and ensembles

A simple way to check whether a variable is *extensive* or *intensive*
is to duplicate a system and to check what happens to the variable. For
example, the volume will double, and the number of particles as well,
but the temperature will remain the same. Volume $V$ and the number of
particles $N$ are extensive variables, and temperature $T$ is an
intensive variable.

1.  Which thermodynamic variables are extensive, and which are
    intensive? Check $V,p,N,$ and $E$. What about the number density
    $\rho\equiv\frac{N}{V}$ and chemical potential $\mu$?

2.  What kind of thermodynamic process is naturally described by the
    Helmholtz free energy? (you may also mention a type of system
    instead)

3.  In terms of which thermodynamic variables is the Helmholtz free
    energy usually expressed?

4.  Calculate the change in free energy $F_B-F_A$ during the isothermal
    expansion of an ideal gas from volume $V_A$ to $V_B$. (Hint: you
    need the ideal gas law.)

5.  What does this amount of energy correspond to? (Hint: you can reuse
    a lot of words from the previous question, but one word is missing.)

6.  Calculate the change in energy $E_B-E_A$ during an adiabatic
    expansion of an ideal gas from volume $V_A$ to $V_B$.

7.  Did you not forget one of the subquestions?

(sec:second_law)=
## The second law of thermodynamics

The second law of thermodynamics can be expressed in different,
equivalent forms. The version by Clausius (1850) states that

> "Heat, by itself, cannot pass from a colder to a hotter body".

Lord Kelvin introduced an equivalent statement

> "A process whose only effect is the complete conversion of heat into
work cannot occur".

1.  Prove that the version of Clausius implies Kelvin's, by showing that
    "not-Kelvin" implies "not-Clausius". In other words (without
    obscure mathematical language) show that if you could build a
    machine that would violate Kelvin's rule, that it would also violate
    the rule of Clausius. (Hint: let this machine power another machine
    pumping heat from a cold to a hot reservoir, and look at the net
    effect of both machines.)

2.  Now prove that Kelvin's rule implies Clausius' (hint: you can
    do something similar as in the previous question). This would finish
    the proof that the two statements are equivalent.

(sec:Carnot_cycle)=
## The Carnot cycle

1.  Sketch the Carnot cycle in a pressure vs. volume diagram, and label
    the thermodynamic processes that are used.

2.  After one cycle, the energy is back to its original value. In other
    words $\oint dE =0$ ($E$ is an equation of state). This implies that
    $\oint dQ = \oint pdV$, meaning that one can convert an amount of
    heat into work (the integrals are along the Carnot cycle, and
    reflect the total change in heat, and the total work being
    performed, respectively). Why is this not in conflict with the
    second law of thermodynamics?

3.  The efficiency of the Carnot cycle is defined as

    $$
      \eta = \frac{W}{Q_\mathrm{H}}.
    $$

    The amount of heat extracted from
    the hot reservoir is $Q_\mathrm{H}$, and $\eta$ represents the
    fraction of that amount that is being converted into work $W$. If
    the Carnot cycle is performed with an ideal gas, one can prove that

    $$
            \eta = 1 - \frac{T_\mathrm{C}}{T_\mathrm{H}}.
    $$ (eq:Carnot_efficiency)

    Show this.
    Hint: This will require a series of steps. First calculate the
    heat exchange and work during each of the four processes of the
    cycle, and use that $W=Q_\mathrm{H}-Q_\mathrm{C}$.

In the last question we made use of the ideal gas law, where we secretly
used the notion of temperature $T$. So secretly, we defined temperature
by the behavior of the ideal gas (in principle one could measure this
directly, by measuring the pressure of a dilute gas). However, one can
also define temperature from the Carnot cycle. See for the explanation
David Tong's reader, section 4.3.2. However, the result is identical to
the one you derived, equation {eq}`eq:Carnot_efficiency`.

(sec:entropy_part_I)=
## Entropy, part I

1.  In a Carnot cycle an amount of heat $Q_\mathrm{H}$ is partially
    converted into work $W$ and partially deposited into a colder
    reservoir, by an amount $Q_\mathrm{C}$. Demonstrate that after one
    cycle

    $$
      \frac{Q_\mathrm{H}}{T_\mathrm{H}} - \frac{Q_\mathrm{C}}{T_\mathrm{C}}=0.
    $$

    (Hint: remember what you derived about the efficiency $\eta$.)

    With a few lines of math one can derive that for *any* reversible
    loop

    $$
      \oint \frac{\mathrm{d}Q}{T} = 0.
    $$

    It seems like there is an equation
    of state. This equation of state is called *entropy* with symbol
    $S$, and $\mathrm{d}Q = T\mathrm{d}S$.

2.  The Carnot cycle is a reversible cycle. One can prove quickly that
    reversible cycles all have the same efficiency, and that this
    efficiency is optimal. Irreversible cycles have a lower efficiency.
    Using this knowledge, we are going to compare two cycles, one being
    the Carnot cycle, the other an irreversible cycle. The irreversible
    cycle extracts an amount of heat $Q'_\mathrm{H}$ and deposits
    $Q'_\mathrm{C}$ and is designed to perform the same amount of work
    as the Carnot cycle (although less efficient), such that
    $Q_\mathrm{H}-Q_\mathrm{C}=Q'_\mathrm{H}-Q'_\mathrm{C}$. Now use
    this to derive that

    $$
      \frac{Q'_\mathrm{H}}{T_\mathrm{H}} - \frac{Q'_\mathrm{C}}{T_\mathrm{C}} \leq 0.
    $$

With some more math one can derive now that for *any* cycle

$$
  \oint \frac{\mathrm{d}Q}{T} \leq 0.
$$

This is called the Clausius
inequality. A consequence is that for an adiabatic process
$S_2\geq S_1$ if the system undergoes a change from state 1 to
state 2.

>    The entropy of an isolated system never decreases.

For a more detailed description of the math, see David Tong's reader
{cite:p}`tong_statphys`, page 122.

## References
```{bibliography}
:style: unsrt
:filter: docname in docnames
```
