+++
title = "Compute differential geometry"
date = 2018-12-29T17:44:21+01:00
weight = 7
#chapter = true
pre = "<b>1.3 </b>"
+++
---

Every analyses using DG can be separated in two phases:

1. Compute differential geometry descriptors
2. descriptor analyses

To get 1. done, just run:
```{bash}
 $ /path/to/FleXgeo/bin/FleXgeo_[MY_OS] -pdb=/path/to/2LJ5.pdb
```

This will generate a bunch of output files and it should not take long to finish the computation.

---

## What are the output files?

The output files are:

* **Diffgeo_xgeo.csv** :  contains the calculated differential geometry descriptors of the input ensemble.
*  Diffgeo_NORM.csv : Same values of "Diffgeo_xgeo,csv" but normalized to [0,1].
*  Diffgeo_MEAN.csv: Mean values of FleXgeo descriptors per residue
*  Diffgeo_STD.csv: Standard deviation of FleXgeo descriptors per residue
*  Diffgeo_VAR.csv: Variation of FleXgeo descriptors per residue
*  DiffgeoStat.lua : The histogram bins position and value of each descriptor for each residue.

The most important file is the **Diffgeo_xgeo.csv**, among other general information extract from the PDB it contain the curvature ($\kappa$), torsion( $\tau$ ), arc-lenght( $s$ ) and writhing number($w$) per residue. The other "diffgeo_*.csv" are self explanatory and the *DiffgeoStat.lua* is gonna be used on the $d_{max}$ computation.  

For this tutorial, we will focus only on the $\kappa$ and $\tau$, more details about $s$ and $w$ will be added in the future.

---
## What did FleXgeo have done?

[DG computation]

---
## Why differential geometry?

[DG quick explanation]
