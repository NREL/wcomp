
# Wakes Compared (wcomp)

Wind farm flow control presents an opportunity to improve the cost of energy and energy yield
of wind farms in specific environments.
A class of software tools that model the effects of wake losses and opportunities for wake
loss mitigation via wind farm flow control has emerged in the past decade.
Many of these tools share key characteristics:
-	Written in the Python programming language
-	Implement multiple steady-state, analytical wake models
-	Target workstation use
-	Integrate with optimization software ecosystems

However, software design decisions and implementation details can lead to discrepancies
and errors across tools that reference corresponding models.
`wcomp` is a Python package that provides an interface to data structures and plotting functions
that enable the comparison of wake model implementations across different software tools.
At its core, `wcomp` provides a set of data structures to contain the results of a
wind farm wake model simulation and a set of plotting functions to inspect these data structures.
Any wind farm wake modeling software that implements the `wcomp` interface can be included
in the comparison directly.

## Integrated software

::::{grid}
:gutter: 3

:::{grid-item-card} [FLORIS](https://github.com/NREL/floris)
![floris](_static/logo_floris.png)
:::

:::{grid-item-card} [FOXES](https://github.com/FraunhoferIWES/foxes)
![foxes](_static/logo_foxes.svg)
:::

:::{grid-item-card} [PyWake](https://gitlab.windenergy.dtu.dk/TOPFARM/PyWake)
![pywake](_static/logo_pywake.svg)
:::
::::

## Installation

Currently, `wcomp` must be installed manually with `pip`. The dependencies are:

- windIO v1.0, can be installed directly from PyPI
- FLORIS v3.6, can be installed directly from PyPI
- foxes v0.6.2, can be installed directly from PyPI
- PyWake v2.5.0 plus three additional commits, must be installed from https://github.com/rafmudaf/PyWake at master branch

Follow these steps to install the dependencies and `wcomp`:
1. Create a new Python environment
2. Install the dependencies:

```bash
pip install windIO
pip install foxes==0.6.2
git clone https://github.com/nrel/floris -b develop && pip install -e floris/
git clone https://github.com/rafmudaf/PyWake && pip install -e PyWake/
```

3. Install `wcomp`:

```bash
pip install -e wcomp
```

## Getting started

See {ref}`wesc2023`, {ref}`torque1turbine`, and {ref}`torque4turbine`.
