+++
title = "Basics"
date = 2018-12-29T17:44:21+01:00
weight = 1
chapter = true
pre = "<b>1. </b>"
+++

### STEP 0

# First things first

This is the documentation page of FleXgeo, this awesome software that let's you compute and analyse proteins conformational ensembles using differential geometry magic. If you are looking for a way to do not need to superimpose structures anymore, this might be the solution you are looking for.

What FleXgeo can do:

 * **Compute a protein backbone differential geometry descriptors**, via a smooth curve representation of backbones.
 * **cluster protein conformations**, via global clustering solution per residue based on its curvature and torsion distribution.
 * **quantify protein residues flexibility**, via the computation of $d_{max}$
 * **compare protein conformations to a reference structure**, via the computation of euclidean distances on the curvature and torsion space.

First, did you read the FleXgeo paper?
If not, I highly recommend you to check the awesome <sup> [1](#footnote1)</sup> paper bellow before proceed.

> [“A superposition free method for protein conformational ensemble analyses and local clustering based on a differential geometry representation of backbone", PROTEINS: Structure, Function, and Bioinformatics, 2018](https://onlinelibrary.wiley.com/doi/abs/10.1002/prot.25652)

This is a basic tutorial designed to be a quick tour on how to use FleXgeo, to achieve that we will reproduce Ubiquitin analyses presented on the FleXgeo paper.
Ok, now that you carefully read the paper and is fully aware of how awesome it is, we can begin our differential geometry witchcraft.


{{% notice note %}}
<a name="footnote1">1</a>: this judgement comes from a completely unbiased place and with no conflict of interest at all.
{{% /notice %}}
