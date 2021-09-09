---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

# Problem set 7

1.  This will lead to

    $$\nabla^2 \psi = - \frac{\rho}{\epsilon_\mathrm{w}}$$

2.  The electric potential energy is

    $$\begin{aligned}
            V_+(z) &= e \psi(z)\\
            V_-(z) &= -e \psi(z)
        \end{aligned}$$

3.  $$\begin{aligned}
            \rho_+(z) &= \rho_{+0} e^{-\beta V_+(z)} = \rho_{+0} e^{-e\psi(z)} \\
            \rho_-(z) &= \rho_{-0} e^{-\beta V_-(z)} = \rho_{-0} e^{e\psi(z)}
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

4.  $$\rho(z) = e \rho_+(z) + (-e)\rho_-(z) = e(\rho_+(z) - \rho_-(z))$$

5.  Far away from the plate, the charge density has to be zero,
    otherwise the system would not be charge neutral. A globally charged
    system has a very high potential energy, that is difficult to
    maintain (think about lightning). Locally, a system can be charged,
    e.g. near the plate.

6.  Substituting the equations for $\rho_+$ and $\rho_-$:

    $$\begin{aligned}
            \psi''(z) &= -\frac{\rho(z)}{\epsilon_\mathrm{w}} \\
            &= - \frac{e}{\epsilon_\mathrm{w}}(\rho_+(z) - \rho_-(z)) \\
            &= -\frac{e}{\epsilon_\mathrm{w}}(\rho_0 e^{-e\psi(z)} - \rho_0 e^{e\psi(z)}) \\
            &= \frac{2e\rho_0}{\epsilon_\mathrm{w}}\sinh{\beta e \psi(z)}         
        \end{aligned}$$

7.  This result is obtained after multiplying both sides of equation
    {eq}`eq:PB_psi` with $\beta e$:

    $$\beta e\psi''(z) = \frac{2\beta e^2\rho_0}{\epsilon_\mathrm{w}}\sinh{\beta e \psi(z)}$$

    and making the substitution. The parameter $\kappa$ is therefore:

    $$\kappa^2 = \frac{2\beta e^2\rho_0}{\epsilon_\mathrm{w}}$$

8.  $$\kappa = \sqrt{\frac{2 e^2\rho_0}{k_\mathrm{B}T\epsilon_\mathrm{w}}}$$

    ($k_\mathrm{B}T = \beta^{-1}$)

9.  If the equation reduces to

    $$\phi''(z) = \kappa^2 \phi(z)$$

    the general solution is

    $$\phi(z) = A e^{-\kappa z} + B e^{\kappa z}$$

10. If the potential is set to zero (or any finite value) in the limit
    to infinity, the constant $B$ has to be zero, so

    $$\phi(z) = A e^{-\kappa z}$$

    With the second condition one can relate $A$ to the surface charge.

    $$E_0 = \frac{\sigma}{\epsilon_\mathrm{w}} = - \psi'(0) = - \frac{\phi'(0)}{\beta e} = \frac{\kappa A}{\beta e}$$

    so

    $$A = \frac{\beta e \sigma}{\kappa \epsilon_\mathrm{w}} = \sqrt{\frac{\sigma^2}{2\rho_0k_\mathrm{B}T\epsilon_\mathrm{w}}}$$

    which is a dimensionless number.

11. This is an exponentially decaying function. See
    {numref}`fig:PB_densities` for the densities.

12. Using that assumption

    $$
    \begin{aligned}
            \rho_-(z) &\approx \rho_0 (1 - A e^{-\kappa z}) \\
            \rho_+(z) &\approx \rho_0 (1 + A e^{-\kappa z})
    \end{aligned}
    $$ 

13. There are a few conversions: $k_\mathrm{B}T = 4 \cdot 10^{-21}$ J at
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

```{code-cell} ipython3
:tags: [hide-input, remove-output]

%config InlineBackend.figure_formats = ['svg']
import numpy as np
import matplotlib.pyplot as plt
from myst_nb import glue

# Densities
A = 0.5 # choose a convenient value for A
z = np.linspace(0,5,100)
negative = 1 - A*np.exp(-z)
positive = 1 + A*np.exp(-z)

## Make the plot
fig, ax = plt.subplots(figsize=(6,4))

ax.plot(z, negative, color='#e96868', label='Negative ions')
ax.plot(z, positive, color='#6a8ba4', label='Positive ions')

ax.legend()

# Labels
ax.set_xlabel(r'$z/\lambda_D$'), ax.set_ylabel(r'$\rho/\rho_0$')

# Limits
ax.set_xlim([0, z[-1]])
ax.set_ylim([0.4, 1.6])

# Save graph to load in figure later (special Jupyter Book feature)
glue("PB_densities", fig, display=False)
```

```{glue:figure} PB_densities
:name: "fig:PB_densities"

The density of positive and negative ions near a charged wall.
```
