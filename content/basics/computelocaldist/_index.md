+++
title = "Comparing residues conformations"
date = 2018-12-29T17:44:21+01:00
weight = 5
#chapter = true
pre = "<b>1.5 </b>"
+++

Another useful analyse is to **compare protein conformations to a reference state**, this can tell if a certain region is stable or if a given conformation is present in your ensemble. The reference state can be either an external reference conformation (ex: a crystallographic structure of the protein bound to a ligand) or some arbitrary conformation which belongs to the ensemble. In both cases, you can use the **'CalcEnsDistFromRef.py'** script to **compute the residues euclidean distance on the $\kappa-\tau$ space**.

---
## How a residue $\kappa-\tau$ space look like?

To check the distribution of a $\kappa$ and $\tau$ of a given residue $t$, you can generate the scatter plot using 'PlotMultiCSVDATA.py' script:

```{bash}
python3 /home/amarinho/EDI02/PosDocBox/FleXgeo/GitHub/FleXgeo/PlotMultiData.py 10 DiffGeo_xgeo.csv:ubq
```

The first argument defines the residue $t$ to be plotted (set 'All' to generate a plot for all residues) and the following arguments are '\<filename_xgeo.csv\>:\<label\>'. We gonna get back to this script latter, but for now lets check the residue 10 $\kappa-\tau$ values distribution.

![plot](./10_MultiCSV_KT.png?width=50pc)

One just need to compute the [euclidean distance](https://en.wikipedia.org/wiki/Euclidean_distance) $d^2$ to compare any pair of residues on this space.   

## How to compute $d^2$?

To compute the local euclidean distance per residue of a arbitrary reference conformation, $c_{ref}$, against all conformations on the ensemble just run:

```{bash}
$ python3 /path/to/FleXgeo/CalcEnsDistFromRef.py -in=XgeoObj.p -refidx=0
```

The reference conformation index is set by the '-refidx' option, the first conformation on the ensemble is 0, the second is 1 and so on. This script will output 'LocalDistFromRef.csv', the distance matrix data, and 'LocalStrucStab_MTX.png', the plot of the matrix (residue, conformation).

![plot](./LocalStrucStab_MTX.png?width=50pc)

Just by checking the matrix is possible to get some insights, for instance, the region around residue 10 do not stay in the same state presented in the first conformation and the same can be said about the region of the C-terminal.

---
{{% notice note %}}


To compute the distance against an external reference state, such as a crystallographic structure, just compute the descriptors of the single structure using FleXgeo and point the path of the '_xgeo.csv' file generated using the '-ext_ref='.  

```{bash}
$ python3 /path/to/FleXgeo/CalcEnsDistFromRef.py -in=XgeoObj.p -ext_ref=/path/to/ref_xgeo.csv
```

{{% /notice %}}


---

## What this script does?

In the DG representation, each residues is represented as a vector, $\vec{x}_t$, defined by it's $\kappa$ and $\tau$ values,

$$ \vec{x}_t = \\{ \kappa_t ,\tau_t \\}$$

therefore, each conformation $c$ can be considered an ordered set $X$ of such vectors

$$X_c = \\{ \vec{x}_1, \vec{x}_2, ..., \vec{x}_N \\}$$

where $N$ is the total number of residues. To compare residues of two conformations $A$ and $B$, one can compute the euclidean distance $d^2$ of equivalent residues vectors

$$ d^{2}(\vec{x}_{t _A} , \vec{x} _{t _B}) = \sqrt{(\kappa _{t _A} - \kappa _{t _B})^2 + (\tau _{t _A} - \tau _{t _B})^2} $$

The script compute $d^{2}$ between residues of the reference conformation and the equivalent residues on all the conformations in the input ensemble.
