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

# Problem set 6

## Problem 6.1

1.  Salt ions disrupt the structure of the water molecules, and
    stimulate the nucleation process. For the formation of a new phase
    (here, a gas bubble) an energy barrier needs to be overcome. Small
    particles or a dirty pan can lower the barrier of the nucleation
    process locally. (this is actually a difficult question, and this
    answer is not the full story)

2.  To prevent the formation of many different crystalline domains,
    which gives an undesirable texture and look, and to make sure that
    one ends up with the ’desirable’ crystalline phase (which forms
    around 32$^\mathrm{o}$C) which is the shiniest and makes the best
    sound when it is broken.

3.  Important is to use a clean bottle, to cool rapidly, and to cool
    deep enough, and not too long, to make sure that the nucleation
    process does not take over.

4.  The formation and growth of ice crystals cuts organic material into
    pieces at a microscopic scale. And if that is not harmful enough, it
    also changes the osmotic pressure in the remaining fluid phase, such
    that cells can dry out or burst.

5.  If one minimises $G$ one finds that

    $$\frac{\partial G}{\partial R} = 0$$

    implies

    $$R_\mathrm{crit} = \frac{\Delta G}{2 \gamma}$$

    How the surface tension $\gamma$ and change in free energy
    $\Delta G$ are calculated is a story for another time.

## Problem 6.2

1.  For an ideal gas

    $$p = k_\mathrm{B}T \rho$$

    and a Van der Waals fluid

    $$p = k_\mathrm{B}T \frac{\rho}{1-b\rho} - a \rho^2$$

2.  See plot at the bottom of this page.

3.  See lecture (slides)

4.  Anywhere where there are multiple densities with the same pressure,
    one could expect a phase coexistence (draw a horizontal line in the
    $p$ vs. $\rho$ curve). However, the regime where the pressure
    decreases with density should not be counted, because these
    densities unstable (see lecture)

5.  For an ideal gas

    $$\mu = k_\mathrm{B}T\ln{\rho}$$

    and for a Van der Waals fluid

    $$\mu = k_\mathrm{B}T\ln\frac{\rho}{1-b\rho} + \frac{k_\mathrm{B}T}{1-b\rho} - 2a\rho$$

6.  See plot at the bottom of this page.

7.  Yes, if there are multiple densities with the same $\mu$ one can
    expect a phase coexistence. The regime where $\mu$ decreases with
    density should not be counted (see part d and lecture slides)

8.  This follows quickly after substituting $\frac{N}{V}$ by $\rho$.

9.  For the pressure (use the sum rule and the chain rule):

    $$p = - \frac{\partial}{\partial V} Vf = - f - V \frac{\partial f}{\partial V} = -f - V \frac{\partial \rho}{\partial V}\frac{\partial f}{\partial \rho} = \rho \frac{\partial f}{\partial \rho} - f$$

    and for $\mu$ similarly:

    $$\mu = \frac{\partial}{\partial N} Vf = V \frac{\partial f}{\partial N} = V \frac{\partial \rho}{\partial N}\frac{\partial f}{\partial \rho} = \frac{\partial f}{\partial \rho}$$

10. It may be obvious that the chemical potentials are the same, because
    $\mu = \frac{\partial f}{\partial \rho}$ is the slope of the curve,
    and the two points obviously have the same slope:

    $$\mu_1 = f'(\rho_1) = f'(\rho_2) = \mu_2$$

    For $p_1 = p_2$ another condition has to be met. If that is the
    case, then

    $$p_1 = \rho_1 f'(\rho_1) - f(\rho_1) =  \rho_2 f'(\rho_2) - f(\rho_2) = p_2$$

    Swapping some terms, gives

    $$\rho_1 f'(\rho_1) - \rho_2 f'(\rho_2) = f(\rho_1) - f(\rho_2)$$

    but we know that $f'(\rho_1)=f'(\rho_2)$, so

    $$f'(\rho_1) = f'(\rho_2) = \frac{f(\rho_1) - f(\rho_2)}{\rho_1 - \rho_2}$$

    This statement tells us that for the pressures to be the same, the
    points need to have the same slope, and in addition to that, that if
    the two points are connected with a straight line, that this line
    has to have the same slope as well. This can be done very easily by
    putting a ruler against the curve of $f(\rho)$, as shown in
    {numref}`fig:free_energy_density`.

```{code-cell} ipython3
:tags: [remove-input]

import numpy as np
import plotly.graph_objects as go
from plotly.subplots import make_subplots
from scipy.optimize import fsolve

kbt = 1

def pressure(rho, a, b):
    p = rho*kbt/(1-b*rho) - a*rho**2
    return p

def chempot(rho, a, b):
    kbt = 1
    mu = kbt*np.log(rho/(1-b*rho)) + kbt*b*rho/(1-b*rho) - 2*a*rho
    return mu

## Define the range of densities to plot
rho = np.linspace(0.01, 0.99, 200)
range_a = np.arange(0, 10, 0.25)

## Create plot
fig = make_subplots(rows=1, cols=2, horizontal_spacing=0.18)

# Add ideal gas traces
fig.add_trace(go.Scatter(
    visible=True,
    x=rho,
    y=pressure(rho, 0, 0),
    line=dict(color="#000000"),
    mode='lines',
    name='Ideal gas'), row=1, col=1)

fig.add_trace(go.Scatter(
    visible=True,
    x=rho,
    y=chempot(rho, 0, 0),
    line=dict(color="#000000"),
    mode='lines',
    name='Ideal gas',
    showlegend=False,), row=1, col=2)

base_traces = 2 # Number of traces that are always visible

# Add traces, one for each slider step
for a in range_a:
    fig.add_trace(        
        go.Scatter(
            visible=False,
            x=rho,
            y=pressure(rho, a, 1),
            line=dict(color="#ff5638"),
            mode='lines',
            name='VdW fluid'), row=1, col=1)

    fig.add_trace(        
        go.Scatter(
            visible=False,
            x=rho,
            y=chempot(rho, a, 1),
            line=dict(color="#ff5638"),
            mode='lines',
            name='VdW fluid',
            showlegend=False), row=1, col=2)

traces_per_step = 2 # Number of traces per value of a

# Show the traces for one value of a when loading the plot (initial setup)
active_a_index = 10
fig.data[active_a_index + base_traces].visible = True
fig.data[active_a_index + base_traces + 1].visible = True

# Create and add slider
steps = []
for i in range(0, range_a.shape[0]):
    visarray = [False] * len(fig.data)
    visarray[0:base_traces] = [True] * base_traces
    curr_idx = int(base_traces + i * traces_per_step)
    next_idx = int(base_traces + (i+1) * traces_per_step)
    visarray[curr_idx:next_idx] = [True] * traces_per_step
    step = dict(
        method="update",
        args=[{"visible": visarray}],
        label=range_a[i]
    )
    steps.append(step)

sliders = [dict(
    active=active_a_index,
    currentvalue={"prefix": "a: "},
    steps=steps
)]

fig.update_layout(
    sliders=sliders,
    legend_title="Legend",
    height=400
)

fig.update_xaxes(title_text=r'$\mathrm{density} \; \rho$', row=1, col=1)
fig.update_xaxes(title_text=r'$\mathrm{density} \; \rho$', row=1, col=2)

# Update yaxis properties
fig.update_yaxes(title_text=r'$\mathrm{pressure} \; p$', range=[-3, 4], row=1, col=1)
fig.update_yaxes(title_text=r'$\mathrm{chemical \; potential} \; \mu$', range=[-5.5, 0.25], row=1, col=2)

fig
```
