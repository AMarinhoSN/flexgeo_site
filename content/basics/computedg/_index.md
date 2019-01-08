+++
title = "Compute differential geometry"
date = 2018-12-29T17:44:21+01:00
weight = 3
#chapter = true
pre = "<b>1.3 </b>"
+++
---
First of all, create a directory and download Ubq ensemble from the pdb by:

```{bash}
mkdir ubq
cd ubq
wget https://files.rcsb.org/download/2LJ5.pdb
```  

Every analyses using DG can be separated in two phases:

1. Differential geometry descriptors computation
2. Descriptor analyses

To get 1. done, just run:
```{bash}
flexgeo -pdb=./2LJ5.pdb
```
{{% notice note %}}
If you did not add the *FleXgeo alias* on the '.bashrc', just use the fullpath.
Check the [installation guide](../installation/) for more information.
{{%/notice %}}

This will generate a bunch of output files and it should finish in a few seconds the computation.

---

## What are the output files?

The output files are:

* **Diffgeo_xgeo.csv** :  contains the calculated differential geometry descriptors of the input ensemble.
*  Diffgeo_NORM.csv : Same values of "Diffgeo_xgeo.csv" but normalized to $\[0,1\]$.
*  Diffgeo_MEAN.csv: Mean values of FleXgeo descriptors per residue
*  Diffgeo_STD.csv: Standard deviation of FleXgeo descriptors per residue
*  Diffgeo_VAR.csv: Variation of FleXgeo descriptors per residue
*  DiffgeoStat.lua : The histogram bins position and value of each descriptor for each residue.

The most important file is the **Diffgeo_xgeo.csv**, among other general information extract from the PDB it contain the curvature ($\kappa$), torsion( $\tau$ ), arc-lenght( $s$ ) and writhing number($w$) per residue. The other "diffgeo_*.csv" are self explanatory and the *DiffgeoStat.lua* is gonna be used on the $d_{max}$ computation.  

For this tutorial, we will focus only on the $\kappa$ and $\tau$, more details about $s$ and $w$ will be added in the future.

---
## What did FleXgeo have done?

In a (pseudo-code) nutshell,

```{python}
for conformation in ensemble:
  > get carbon alpha coordinates xyz
  > get curve backbone representation via cubic splice interpolation

    for residue in conformation:
      > compute descriptors
      > store results

> compute histogram
```
