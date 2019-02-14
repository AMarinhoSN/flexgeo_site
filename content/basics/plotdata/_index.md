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

## So what does that mean?

The plot might be not very informative at first glance, but to interpret it first we need to understand the meaning of curvature, $\kappa$, and torsion, $\tau$, values. The [wikipedia article on differential geometry of spatial curves](https://en.wikipedia.org/wiki/Differential_geometry_of_curves) is a very decent introduction which also include the mathematics behind it and you should check it, but for this tutorial let's try to keep it brief and simple. To understand what $\kappa$ and $\tau$ actually means, first we need to understand how such quantities are defined and they are defined based on the **framing of a curve**.

#### framing of a curve

The framing of a curve means we need to define a set of vectors that can be computed for each point along the regular spatial curve, $r$, and by monitoring how such set of vectors changes along such curve characterize its shape. The 'along the curve' part can be more objectively specified by the arc-length, $s$, as $r$ is just a function that map some values on the interval $I$, we can parametrize $\vec{r}$ as a function of $s$ or, as mathematicians like to call it,
$$ r : I \rightarrow R^{3} $$
$$\vec{r}(s) : I \rightarrow R^{3}$$.

The standard choice for framing a curve is to use [the frenet-serret frame](https://en.wikipedia.org/wiki/Frenet%E2%80%93Serret_formulas), which defines 3 unit vectors: tangent ($\vec{T}$), normal($\vec{N}$) and binormal($\vec{B}$) unit vectors). If the analysed curve, $\vec{r}(s)$ represents a particle trajectory, the tangent vector will always point in the direction of the motion of the particle and the binormal vector would always point in the "up" direction from the particle frame of reference, check the animation.

![fs-frame](https://upload.wikimedia.org/wikipedia/commons/1/14/Frenet-Serret-frame_along_Vivani-curve.gif)


Now imagine that this particle just move in a straight line trajectory without any rotational motion. For such case the, $\vec{T}$ and $\vec{B}$ will be constant. On the other hand, if the particle moves on a non straight line trajectory but keep in the exact same plane, $\vec{T}$ will change while $d\vec{B}$ will still be constant. Considering these features, is possible tu use $\vec{T}$ and $\vec{B}$ to define quantities that measures how much a given point in a curve deviates from a straight line and from a plane.

#### defining $\kappa$ and $\tau$
Let's first start with **curvature**, $\kappa$. We can define $\kappa$ as a measurement of how much a point in a given curve deviates from straight line by considering as a measurement of how much $\vec{T}$ changes along the curve by:
$$
\kappa = \| \vec{\kappa}(s) \| = \| \frac{d\vec{T}}{ds} \|
$$

if $\kappa = 0$ for a given point $t$, then the curve will be a perfect straight line at $t$. As higher the $\kappa$ values, the higher will be the change of $\vec{T}$ at the vicinity of $t$. Therefore, if a $\kappa$ spike at point $t$ appears in your curve, this means that at point $t$ there is a abrupt change in the direction of the curve. Similarly, the same rationale can be applied to planes by defining the **Torsion**, $\tau$, as
$$
\tau = \| \vec{\tau} \| = \| \frac{d\vec{B}}{ds} \|
$$

If a $\tau$ spike at point $t$ appears in your curve, this means that at point $t$ there is an abrupt change in the plane in the vicinity of $t$. With those to descriptors one can uniquely characterize any 3D regular curve via $\kappa$ and $\tau$ as a function of $s$. For instance, check how the $\kappa$ and $\tau$ values of a Torus knots relate to its Frenet-Serret frame in the animation bellow.

![gif](https://upload.wikimedia.org/wikipedia/commons/6/68/Torus-Knot_uebereinander_animated.gif)

With that in mind you should be able to look to the plot generated and have an idea of what it means.

## What about the plot?

The plot generate express the $\kappa$ and $\tau$ values per residue $t$ for all conformations of the ensemble. Each line of the plot is the representation of a single conformation and how much a residue change its "signature" give you an idea of its flexibility and what is happening. For instance, just by looking at the plot you can claim that residues 24 to 34 are a stable helix, that the last residues are more flexible and the region around residue 10 present a higher flexibility than the rest of the protein and residues 36 and 60 are stable points of inflection in the backbone. Look at the ensemble on Pymol and check if our interpretation make sense ;).
