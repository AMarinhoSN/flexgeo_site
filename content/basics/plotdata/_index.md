+++
title = "Plot and understand the data"
date = 2018-12-29T17:44:21+01:00
weight = 4
#chapter = true
pre = "<b>1.4 </b>"
+++

Now we have the data computed, so the first thing to do is check how it looks like. You can plot the data from 'Diffgeo_xgeo.csv' using any software or script you like, but on FleXgeo you find a script to generate some plots and you can run it using:

```{bash}
$ python3 /path/to/FleXgeo/PlotFXgeoData.py DiffGeo_xgeo.csv
```

This script will generate the plot bellow

![plot](./KTrawData.png?width=50pc)

---

## So what does that even mean?

The plot might be not very informative at first glance, but to interpret it first we need to understand the meaning of curvature, $\kappa$, and torsion, $\tau$, values. The [wikipedia article on differential geometry of spatial curves](https://en.wikipedia.org/wiki/Differential_geometry_of_curves) is a very decent introduction which also include the mathematics behind it and you should check it, but for this tutorial let's try to keep it brief and simple. To understand what $\kappa$ and $\tau$ actually means, first we need to understand how such quantities are defined and they are defined based on the **framing of a curve**.

#### framing of a curve

The framing of a curve means we need to define a set of vectors that can be computed for each point along the regular spatial curve, $r$, and by monitoring how such set of vectors changes along such curve characterize its shape. The 'along the curve' part can be more objectively specified by the arc-length, $s$, as $r$ is just a function that map some values on the interval $I$, we can parametrize $\vec{r}$ as a function of $s$ or, as mathematicians like to call it,
$$ r : I \rightarrow R^{3} $$
$$\vec{r}(s) : I \rightarrow R^{3}$$.

The standard choice for framing a curve is to use [the frenet-serret frame](https://en.wikipedia.org/wiki/Frenet%E2%80%93Serret_formulas), which defines 3 unit vectors: tangent ($\vec{T}$), normal($\vec{N}$) and binormal($\vec{B}$) unit vectors). If the analysed curve, $\vec{r}(s)$ represents a particle trajectory, the tangent vector will always point in the direction of the motion of the particle and the binormal vector would always point in the "up" direction from the particle frame of reference, check the animation.

![fs-frame](https://upload.wikimedia.org/wikipedia/commons/1/14/Frenet-Serret-frame_along_Vivani-curve.gif)


Now imagine that this particle just move in a straight line trajectory without any rotational motion. For such case the, $\vec{T}$ and $\vec{B}$ will be constant and equal to zero.



[...with such vectors now is possible to define our beloved quantities]

#### defining $\kappa$ and $\tau$

$\kappa$ reflects how much a given curve deviates from a straight line, if $\kappa = 0$, then the curve will be a perfect straight line at  

![gif](https://upload.wikimedia.org/wikipedia/commons/6/68/Torus-Knot_uebereinander_animated.gif)

## That's nice, but so what?

[comment specific aspects of the plot and how it relate to the structure]
For example, at residues 24-34  
A little breakdown
