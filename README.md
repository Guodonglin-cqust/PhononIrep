# PhononIrep

A phonon irreducible representations calculator([arXiv2201.11350](https://arxiv.org/pdf/2201.11350.pdf)).

# Installation
One need install both Python and Mathematica.
## Configure Python
First you should install python and phonopy.
e.g. install the Anaconda or miniconda, and run 
```
conda install -c conda-forge phonopy
```
To interface with Mathematica one need also install pyzmq by
```
pip install pyzmq 
```
## Configure Mathematica
Copy the SpaceGroupIrep direcory and PhononIrep.wl into any of the Mathematica `$Path` direcory.

That all for installation

# Installation for Linux and Mac
The installation step for Linux and Mac is simllar to Windows.


# Run PhononIrep


One can open a Mathematica notebook and run
```
path = "D:\\Anaconda3"
SetEnvironment["PATH" -> Environment["PATH"] <> ";" <> path <> "\\Library\\bin"];
RegisterExternalEvaluator["Python", path <> "\\python.exe"];
Needs["PhononIrep`"]
```
to import PhononIrep. Here, one need to modify the `path` to the Python installation direcory. For Linux and Mac `python.exe` should be modfied by `python`, and run 
```
calcPhononIrep["supercell" -> {2, 2, 1},
 "unitcell" -> NotebookDirectory[] <> "POSCAR-unitcell",
 "force" ->  NotebookDirectory[] <> "FORCE_CONSTANTS",
 "kset" -> {{0,0,0}},
 "showRep" -> True
 ]
 ```
 to calculate the irreducible representations of Gamma point of given structure.
