
# Architecture and Design

`wcomp` entirely consists of an interface definition to wake modeling software, a module of data
structures to hold wind farm wake simulation results, and plotting functions.
The ultimate objective is to provide infrastructure to obtain consistence results from
similar wake modeling software with common inputs.
Each wake modeling software that implements the interface can be automatically included in
the dataset of solutions to characteristic problems.

The package diagram below shows the modules within `wcomp` and how each relates to the
others as dependencies (which modules import which other modules).

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

The interface to implement by participating wake modeling software is defined in an abstract
base class, `wcomp.base_interface`, and the class diagram is given below.

````{card} WCompBase Class Diagram
:width: 75%
:margin: auto

```{mermaid} ../wcomp/WCompBase.mmd
```
````

The following table maps the wake modeling software currently integrated to `wcomp` to the
API documentation for their respective interface files, for reference.

| Wake Model | Interface File |
|------------|----------------|
| [Floris](https://github.com/NREL/floris) | {py:class}`wcomp.floris_interface` |
| [foxes](https://github.com/FraunhoferIWES/foxes) | {py:class}`wcomp.foxes_interface` |
| [PyWake](https://gitlab.windenergy.dtu.dk/TOPFARM/PyWake) | {py:class}`wcomp.pywake_interface` |

<!-- ```{autoclasstree} wcomp.base_interface
``` -->

<!-- ```{mermaid} ../wcomp/classes.mmd
:zoom:
``` -->
