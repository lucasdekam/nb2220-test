# Ionic screening

The goal of this exercise is to estimate the length over which electric
fields can extend in electrolyte solutions. It is known since the
experiments of Charles-Auguste de Coulomb that the electric force
between two charged spheres depends on the inverse distance squared, or,

$$
    F\propto \frac{1}{r^2}
$$

and so does the electric field around a
charged sphere or point charge. In vacuum or air, there is no typical
"range" of the electric field. The length over which you could measure
the field would depend on the quality of the device you are using, or
the strength of the charge. This is different for electric fields in
electrolyte solutions, where electric fields drop to zero after a
well-defined length, because of the influence of the ions. This length
is usually much smaller than a micrometer in water, and depends on the
concentration of electrolytes.

In this exercise we will calculate the density of ions near a charged
plate, e.g. an electrode. The plate has a surface charge density
$-\sigma$, is immersed in a solution with dielectric permittivity
$\epsilon_\mathrm{w}$, and salt concentration of 0.1 M. The ions are
monovalent, i.e. their charge is $+e$ or $-e$, with $e$ the elementary
charge. A schematic picture is shown in {numref}`fig:Screening_schematic`.

```{figure} images/screening.svg
---
name: fig:Screening_schematic
width: 50%
---
Schematic depiction of a distribution of ions near a flat surface with negative
charge.
```

1.  Express the law of Gauss

    $$
        \vec{\nabla} \cdot \vec{E} = \frac{\rho}{\epsilon_\mathrm{w}}
    $$

    in terms of the electric potential $\psi$, with
    $\vec{E} = -\vec{\nabla} \psi$. This law is referred to as Poisson's
    law. The symbol $\rho$ stands for the charge density.

2.  What is the potential energy of a positive ion, and what of a
    negative ion, at a distance $z$ from the plate? (Express the answer
    in terms of the electric potential $\psi(z)$.)

3.  What would be the density of ions as a function of $z$, in terms of
    the potential $\psi(z)$, if one would use the Boltzmann
    distribution? (This is actually a terribly difficult question,
    which has not completely been solved after a century of literature.
    A couple of hints will be given: Remember that the Boltzmann
    distribution is

    $$
        P_n = \frac{1}{Z}e^{-\beta E_n}
    $$

    where $n$ is the
    state of the system, and $E_n$ the energy of that state. If the
    particles would not interact with each other, then the density of
    positive ions would be

    $$
        \rho_+(z) = \rho_{+0} e^{-\beta V_+(z)}
    $$ (eq:Boltzmann_distribution_ions)

    with $\rho_+(z)$
    in units of number per volume, $V_+(z)$ the potential energy of a
    positive ion at position $z$, and $\rho_{+0}$ the density far away
    from the plate, where $V_+(z)$ is set to zero. Of course, the ions
    do interact with each other, and that makes the question very
    difficult. A more appropriate distribution would be

    $$
        \rho_+(z) = \rho_{+0} e^{-\beta (V_\mathrm{plate}(z) + V_\mathrm{int}(z))}
    $$

    where $V_\mathrm{plate}(z)$ is the potential energy of an ion,
    caused by the plate, and $V_\mathrm{int}(z)$ is the average
    potential energy from the interaction between an ion at position $z$
    and all the other ions. This second term is very difficult to
    calculate, without making assumptions. For now, we will assume that
    we can use {eq}`eq:Boltzmann_distribution_ions`, with $V_+(z)$ as found
    in the previous question.)

4.  What would be the charge density at position $z$?

5.  Argue why the constants $\rho_{+0} = \rho_{-0}$. Call
    $\rho_{+0}\equiv\rho_0$.

6.  Express Poisson's law in terms of $\rho_+(z)$ and $\rho_-(z)$, and
    derive the second order differential equation for $\psi(z)$

    $$
        \psi''(z) = \frac{2e\rho_0}{\epsilon_\mathrm{w}}\sinh{\beta e \psi(z)}
    $$

    using the relation $2\sinh{x}=e^x - e^{-x}$.

7.  Rewrite the equation in terms of the variable
    $\phi(z)\equiv\beta e \psi(z)$ (which can be interpreted as the
    potential energy of a positive ion at position $z$ in units of
    $k_\mathrm{B}T$) in the form:

    $$
        \phi''(z) = \kappa^2 \sinh{\phi(z)}
    $$ (eq:PB)

    This equation is
    referred to as the \"Poisson-Boltzmann equation\", because it
    combines the Poisson equation (for the electric potential) with the
    Boltzmann distribution (for the ions). The Boltzmann distribution of
    the ions is approximated here.

8.  What is $\kappa$ in terms of the system parameters?

9.  If $\phi < 1$ one can approximate $\sinh{\phi}\approx \phi$. Find
    the general solution of the differential equation for small
    $\phi<1$.

10. Use the boundary conditions to find the solution specific to this
    system. Hint: make sure that the electric potential goes to zero
    for large $z$ and that the electric field at $z=0$ obeys
    $E_0 = \frac{\sigma}{\epsilon_\mathrm{w}}$.

11. Sketch this function, and find the distance over which the density
    drops by a factor $e^{-1}$. This distance is known as the "Debye
    screening length" named after Pieter Debye.

12. Sketch the density of positive and negative ions near the plate.
    Hint: you can use the assumption that $\phi\ll1$.

13. Calling this distance $\lambda_\mathrm{D} \equiv \kappa^{-1}$, what
    is the screening length in water, with a concentration of 100 mM
    sodium chloride? And what for 1 mM? Hint: to convert molar density
    to number density, one simply has to multiply by Avogadro's number
    $6.022\cdot10^{23}$. It should be roughly between 0.1 and 100 nm, in
    case the calculated number would fall outside this interval.

In this specific case, there is also an analytical solution to equation
{eq}`eq:PB`, but the
solution is only different from the one you calculated if $\phi>1$,
which can only occur close to the plate, say $z < \lambda_\mathrm{D}$.
Even though we made a convenient assumption in part (c), the expression
for the screening length that you calculated is still a very useful
estimate for how far electric fields extend in electrolyte solutions,
and how far charged particles such as proteins can interact with each
other. What happens within that distance can be very complicated,
especially when the electrolytes interact more strongly, such as
Ca$^{2+}$ ions and ions in other solutions with a smaller dielectric
constant. Also, it takes some time for the ions to screen a charged
object, because they have to diffuse over some distance (of the order of
a few nanoseconds at 0.1 M). Therefore, quickly varying fields can
penetrate deeper into an electrolyte solution, and can also be
disruptive for cell membranes. This phenomenon is known as
electroporation. And there are many more interesting effects that rely
on the response of electrolytes, that the body uses for many purposes.
But that is a story for another time...
