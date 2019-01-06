+++
title = "Quick guide"
date = 2018-12-29T17:44:21+01:00
weight = 3
#chapter = true
pre = "<b>3. </b>"
+++
---

If you are just looking for some list of commands to run, don't be ashamed, nobody will judge you. I know you just want the "how to", but If you have no idea of "what is" and "why to" use FleXgeo, you should check [**FleXgeo paper**](https://onlinelibrary.wiley.com/doi/abs/10.1002/prot.25652) and the [**Basic tutorial**](../basics/).

* Calculate Differential Geometry

```{bash}
$ /path/to/FleXgeo/bin/FleXgeo_[MY_OS] -pdb=ensemble.pdb [options]
```
  FleXgeo accepts the following arguments:

|    OPTIONS       | DESCRIPTION               | DEFAULT                 |
|----------------|-----------------------------|--------------------------|
|-pdb=[filename.pdb]|Set input .pdb filename|User must provide  |
|-ncpus=[int]      |Set the number of cpus FleXgeo will use | All cpus available|
|-isSingle        |Indicate if input pdb is a single conformation pdb | FALSE|
|-outprfx=[prefix] | Set the output files prefix to be used | 'Diffgeo_' |

* Plot xgeo data
```{bash}
$ python3 /path/to/PlotFXgeoData.py DiffGeo_xgeo.csv
  ```

* Calculate distance between all conformations and a reference conformation on the ensemble.
 ```{bash}
 $ python3.5 /path/to/FleXgeo/CalcEnsDistFromRef.py -in=XgeoObj.p
 ```

* Calculate distance between all conformations and an external reference conformation
 ```{bash}
 $ python3.5 /path/to/FleXgeo/CalcEnsDistFromRef.py -in=XgeoObj.p -ext_ref=/path/to/ref_xgeo.csv
 ```

* Calculate residues $d_{max}$
  ```{bash}
  $ luajit /path/to/FleXgeo/HistProc.lua
  $ python3.5 /path/to/FleXgeo/ComputeResDMax.py
  ```

* Clustering conformations
 ```{bash}
 $ python3.5 /path/to/FleXgeo/GetResClusters.py -res ALL DiffGeo_xgeo.csv -min_pcluster .05
 ```
* Write cluster pdbs
 ```{bash}
 $ python3.5 /path/to/FleXgeo/WriteClustersPDB.py cluster.clstr source.pdb res
 ```
