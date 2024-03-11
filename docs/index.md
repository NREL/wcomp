
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

The wake modeling software currently integrated to `wcomp` are:
- [Floris](https://github.com/NREL/floris)
- [FOXES](https://github.com/FraunhoferIWES/foxes)
- [PyWake](https://gitlab.windenergy.dtu.dk/TOPFARM/PyWake)

The package diagram below shows the modules within `wcomp` and how each relates to the
others as dependencies (in other words, which modules import which other modules).

```{mermaid}
classDiagram
  wcomp --> floris_interface
  wcomp --> foxes_interface
  wcomp --> pywake_interface
  base_interface --> output_struct
  floris_interface --> base_interface
  floris_interface --> output_struct
  floris_interface --> plotting
  foxes_interface --> base_interface
  foxes_interface --> output_struct
  foxes_interface --> plotting
  plotting --> output_struct
  pywake_interface --> base_interface
  pywake_interface --> output_struct
  pywake_interface --> plotting
```

# Getting started
Here's how to get started