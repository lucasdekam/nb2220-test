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

```{code-cell} ipython3
:tags: [hide-input]

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
    xaxis_title=r'$\mathrm{density} \; \rho$',
    yaxis_title=r'$\mathrm{pressure} \; p$',
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
