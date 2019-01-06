# FleXgeo

FleXgeo is a software package design to compute and analyze a protein conformational ensembles using a differential geometry representation of protein backbone. The current available version is the prototype software written to compute all analyses presented at:

> [“A superposition free method for protein conformational ensemble analyses and local clustering based on a differential geometry representation of backbone", PROTEINS: Structure, Function, and Bioinformatics, 2018](https://onlinelibrary.wiley.com/doi/abs/10.1002/prot.25652)

While is fully functional, keep in mind that this prototype was written to fulfill the authors own selfish desires. We try our best to make it usable to others outside our group, but there are a lot to improve on different aspects.


## Main Features

Currently, there are ready to use scripts to:

  * **cluster protein conformations**, via global clustering solution per residue based on its curvature and torsion distribution.
  * **quantify protein residues flexibility**, via the computation of $d_{max}$
  * **compare protein conformations to a reference structure**, via the computation of euclidean distances on the curvature and torsion space.

FleXgeo code was written by [PhD. Antonio Marinho da Silva Neto](https://amarinhosn.github.io/) and PhD. Rinaldo Wander Montalvao.

{{% notice note %}}
FleXgeo is under development and more features beyond the presented in the paper are planned to be added. If you want to be informed right away when a new feature is added you can *star* [FleXgeo repository on github](https://github.com/AMarinhoSN/FleXgeo) or simply check this page from time to time.
{{% /notice %}}


Here you can find:

* Installation Instructions
* A basic usage manual
* Tutorials

## Teach me the ways of FleXgeo
If you want a step by step guide, check [The Basics](./basics/)


## I know what I am doing
If you know what you are doing and just want some quick and dirt command list to run, check the **Quick and dirty guide**.

## I want to speak to the manager
Do you follow the instructions here and find unexpected errors, bugs, or have suggestion on how to make FleXgeo great again or, even better, simply want to express how grateful you are for this awesome software, please feel free to contact Antonio Marinho at `a.marinho@cent.uw.edu.pl` or use the [FleXgeo github page](https://github.com/AMarinhoSN/FleXgeo) and create a new issue.
