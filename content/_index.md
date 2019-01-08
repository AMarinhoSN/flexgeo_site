# FleXgeo

FleXgeo is a software package design to compute and analyse protein conformational ensembles using a differential geometry (DG) representation of protein backbone. The current available version is the prototype software written to compute all analyses presented at:

> [“A superposition free method for protein conformational ensemble analyses and local clustering based on a differential geometry representation of backbone", PROTEINS: Structure, Function, and Bioinformatics, 2018](https://onlinelibrary.wiley.com/doi/abs/10.1002/prot.25652)

While fully functional, keep in mind that this prototype was written to fulfil the authors own selfish desires. We try our best to make it usable to others outside our group, but for sure there are a lot to improve. If you have any suggestions, feel free to contact Antonio Marinho at `a.marinho@cent.uw.edu.pl`.

Here you can find:

* [Installation instructions](./installation/)
* [A basic usage tutorial](./basic/)
* [Quick command list](./quickguide/)


## Main Features

Currently, FleXgeo is able to:

  * **Compute backbone DG**, compute differential geometry descriptors of protein conformations backbones.
  * **cluster protein conformations**, via global clustering solution per residue based on its curvature and torsion distribution.
  * **quantify protein residues flexibility**, via the computation of $d_{max}$
  * **compare protein conformations to a reference structure**, via the computation of euclidean distances on the curvature and torsion space.

FleXgeo code was written by [PhD. Antonio Marinho da Silva Neto](https://amarinhosn.github.io/) and PhD. Rinaldo Wander Montalvao.

{{% notice note %}}
FleXgeo is under development and more features beyond the presented in the paper are planned to be added. If you want to be informed right away when a new feature is added you can *star* [FleXgeo repository on github](https://github.com/AMarinhoSN/FleXgeo) or simply check this page from time to time.
{{% /notice %}}


## Tutorials
If you want a step by step guide, check the [**Basic Tutorial**](./basics/). If you know what you are doing and just want some quick command list to run, check the [**Quick and dirty guide**](./quickguide/).

## Bugs/Suggestions/Comments
Do you follow the instructions here and find unexpected errors, bugs, or have suggestion on how to make FleXgeo great again or, even better, simply want to express how grateful you are for this awesome software, please feel free to contact Antonio Marinho at `a.marinho@cent.uw.edu.pl` or use the [FleXgeo github page](https://github.com/AMarinhoSN/FleXgeo) and create a new issue.

## How to cite?

If you published results produced by FleXgeo, please cite:

> Marinho da Silva Neto, Antonio, et al. ‘A Superposition Free Method for Protein Conformational Ensemble Analyses and Local Clustering Based on a Differential Geometry Representation of Backbone’. Proteins: Structure, Function, and Bioinformatics, Dec. 2018. Crossref, doi:10.1002/prot.25652.

A bibtex entry:
```
@article{amarinho2018,
	title = {A superposition free method for protein conformational ensemble analyses and local clustering based on a differential geometry representation of backbone},
	issn = {08873585},
	url = {http://doi.wiley.com/10.1002/prot.25652},
	doi = {10.1002/prot.25652},
	language = {en},
	urldate = {2019-01-02TZ},
	journal = {Proteins: Structure, Function, and Bioinformatics},
	author = {Marinho da Silva Neto, Antonio and Silva, Samuel Reghim and Vendruscolo, Michele and Camilloni, Carlo and Montalvao, Rinaldo Wander},
	month = dec,
	year = {2018}
}
```
