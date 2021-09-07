Ionic screening {#ionic-screening .unnumbered}
===============

![Animation of a distribution of ions near a flat surface with negative
charge.](book-tudelft-latex-v3-TI/Exercise_set_7/NB2220_Screening.png "fig:")
[fig:Screening~s~chematic]

1.  Express the law of Gauss

    $$\vec{\nabla} \cdot \vec{E} = \frac{\rho}{\epsilon_\mathrm{w}}$$

    in terms of the electric potential $\psi$, with
    $\vec{E} = -\vec{\nabla} \psi$. This law is referred to as Poisson’s
    law. The symbol $\rho$ stands for the charge density.

    This will lead to

    $$\nabla^2 \psi = - \frac{\rho}{\epsilon_\mathrm{w}}$$

2.  What is the potential energy of a positive ion, and what of a
    negative ion, at a distance $z$ from the plate? (express the answer
    in terms of the electric potential $\psi(z)$)

    The electric potential energy is

    $$\begin{aligned}
            V_+(z) &=& e \psi(z)\\
            V_-(z) &=& -e \psi(z)
        \end{aligned}$$

3.  What would be the density of ions as a function of $z$, in terms of
    the potential $\psi(z)$, if one would use the Boltzmann
    distribution?

    $$\begin{aligned}
            \rho_+(z) &=& \rho_{+0} e^{-\beta V_+(z)} = \rho_{+0} e^{-e\psi(z)} \\
            \rho_-(z) &=& \rho_{-0} e^{-\beta V_-(z)} = \rho_{-0} e^{e\psi(z)} 
        \end{aligned}$$

    with $\rho_+(z)$ in units of number per volume, $V_+(z)$ the
    potential energy of a positive ion at position $z$, and $\rho_{+0}$
    the density far away from the plate, where $V_+(z)$ is set to zero.
    These expressions are approximately correct, if the interactions
    between the ions are weak enough. Of course, ions interact with each
    other, and that makes it very difficult to solve the question
    exactly. This type of approximation is called a “mean field”
    approximation, and is a topic for an advanced statistical mechanics
    course.

4.  What would be the charge density at position $z$?

    $$\rho(z) = e \rho_+(z) + (-e)\rho_-(z) = e(\rho_+(z) - \rho_-(z))$$

5.  Argue why the constants $\rho_+0 = \rho_-0$. Call
    $\rho_+0\equiv\rho_0$

    Far away from the plate, the charge density has to be zero,
    otherwise the system would not be charge neutral. A globally charged
    system has a very high potential energy, that is difficult to
    maintain (think about lightning). Locally, a system can be charged,
    e.g. near the plate.

6.  Express Poisson’s law in terms of $\rho_+(z)$ and $\rho_-(z)$, and
    derive the second order differential equation for $\psi(z)$

    $$\label{eq:PB_psi}
            \psi''(z) = \frac{2e\rho_0}{\epsilon_\mathrm{w}}\sinh{\beta e \psi(z)}$$

    using the relation $2\sinh{x}=e^x - e^{-x}$.

    Substituting the equations for $\rho_+$ and $\rho_-$:

    $$\begin{aligned}
            \psi''(z) &=& -\frac{\rho(z)}{\epsilon_\mathrm{w}} = - \frac{e}{\epsilon_\mathrm{w}}(\rho_+(z) - \rho_-(z)) \\
            &=& -\frac{e}{\epsilon_\mathrm{w}}(\rho_0 e^{-e\psi(z)} - \rho_0 e^{e\psi(z)}) \\
            &=& \frac{2e\rho_0}{\epsilon_\mathrm{w}}\sinh{\beta e \psi(z)}         
        \end{aligned}$$

7.  Rewrite the equation in terms of the variable
    $\phi(z)\equiv\beta e \psi(z)$ (which can be interpreted as the
    potential energy of a positive ion at position $z$ in units of
    $k_\mathrm{B}T$) in the form:

    $$\label{eq:PB}
            \phi''(z) = \kappa^2 \sinh{\phi(z)}$$

    This equation is referred to as the “Poisson-Boltzmann equation”,
    because it combines the Poisson equation (for the electric
    potential) with the Boltzmann distribution (for the ions). The
    Boltzmann distribution of the ions is approximated here.

    This result is obtained after multiplying both sides of equation
    [eq:PB~p~si] with $\beta e$:

    $$\beta e\psi''(z) = \frac{2\beta e^2\rho_0}{\epsilon_\mathrm{w}}\sinh{\beta e \psi(z)}$$

    and making the substitution. The parameter $\kappa$ is therefore:

    $$\kappa^2 = \frac{2\beta e^2\rho_0}{\epsilon_\mathrm{w}}$$

8.  What is $\kappa$ in terms of the system parameters?

    $$\kappa = \sqrt{\frac{2 e^2\rho_0}{k_\mathrm{B}T\epsilon_\mathrm{w}}}$$

    ($k_\mathrm{B}T = \beta^{-1}$)

9.  If $\phi < 1$ one can approximate $\sinh{\phi}\approx \phi$. Find
    the general solution of the differential equation for small
    $\phi<1$.

    If the equation reduces to

    $$\phi''(z) = \kappa^2 \phi(z)$$

    the general solution is

    $$\phi(z) = A e^{-\kappa z} + B e^{\kappa z}$$

10. Use the boundary conditions to find the solution specific to this
    system. [hint: make sure that the electric potential goes to zero
    for large $z$ and that the electric field at $z=0$ obeys
    $E_0 = \frac{\sigma}{\epsilon_\mathrm{w}}$]

    If the potential is set to zero (or any finite value) in the limit
    to infinity, the constant $B$ has to be zero, so

    $$\phi(z) = A e^{-\kappa z}$$

    With the second condition one can relate $A$ to the surface charge.

    $$E_0 = \frac{\sigma}{\epsilon_\mathrm{w}} = - \psi'(0) = - \frac{\phi'(0)}{\beta e} = \frac{\kappa A}{\beta e}$$

    so

    $$A = \frac{\beta e \sigma}{\kappa \epsilon_\mathrm{w}} = \sqrt{\frac{\sigma^2}{2\rho_0k_\mathrm{B}T\epsilon_\mathrm{w}}}$$

    which is a dimensionless number.

11. Sketch this function, and find the distance over which the density
    drops by a factor $e^{-1}$. This distance is known as the “Debye
    screening length” named after Pieter Debye.

    This is an exponentially decaying function. See figure
    [fig:PB~d~ensities] for the densities.

12. Sketch the density of positive and negative ions near the plate.
    [hint: you can use the assumption that $\phi\ll1$]

    Using that assumption

    $$\begin{aligned}
     \label{eq:PB_densities}
            \rho_-(z) &\approx& \rho_0 (1 - A e^{-\kappa z})\\
            \rho_+(z) &\approx& \rho_0 (1 + A e^{-\kappa z})
        \end{aligned}$$

    ![The density of positive and negative ions near a charged
    wall.](book-tudelft-latex-v3-TI/Exercise_set_7/NB2220_PB_density.png "fig:")
    [fig:PB~d~ensities]

13. Calling this distance $\lambda_\mathrm{D} \equiv \kappa^{-1}$, what
    is the screening length in water, with a concentration of 100 mM
    sodium chloride? And what for 1 mM? [hint: to convert molar density
    to number density, one simply has to multiply by Avogadro’s number
    $6.022\cdot10^{23}$. It should be roughly between 0.1 and 100 nm, in
    case the calculated number would fall outside this interval]

    There are a few conversions: $k_\mathrm{B}T = 4 \cdot 10^{-21}$ J at
    room temperature, 0.1 M is equal to $6.022\cdot10^{25}$ particles
    per m$^3$ (convert from liter to get the S.I. unit), the dielectric
    constant of water is (depending on circumstances)
    $\epsilon_\mathrm{w} = 80 \epsilon_0 = 7\cdot10^{-10}\ \frac{\mathrm{C}^2}{\mathrm{N}\mathrm{m}^2}$.
    The screening length at 0.1M at room temperature and ambient
    pressure is therefore $\lambda_\mathrm{D} \approx 1$ nm.

    The screening length
    $\lambda_\mathrm{D} \propto \frac{1}{\sqrt{\rho_0}}$, so if the
    density decreases by a factor 100, the screening length increases by
    a factor 10, so $\lambda_\mathrm{D} \approx 10$ nm at 1 mM.


