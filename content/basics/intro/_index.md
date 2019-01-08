+++
title = "Introduction"
date = 2018-12-29T17:44:21+01:00
weight = 1
#chapter = true
pre = "<b>1.1 </b>"
+++

On this basic tutorial, we will reproduce the analyses of the Ubiquitin ensemble presented at FleXgeo paper. The Ubiquitin (Ubq) is a good example of a **regular rigid globular protein with a flexible C-terminal tail**. This is a fairly simple and common analyses scenario on protein structural biology projects, therefore a good place to start. As on any data analyses scenario, before we start to do anything at all let's first understand our general questions, goals and the "what/why/how" differential geometry can be useful.

---

## What we want to know?

Flexibility is an important aspect of protein function and let's assume that for some reason you are interest on Ubq C-terminal tail dynamics. Maybe you found experimental evidence that mutations on this region affects Ubq binding capabilities and want to know how flexible it actually is and which residues are more important.

---

## What data do we have?

Fortunately, there is an Ubq conformational ensemble obtained based on NMR-restrained metadynamics available at Protein Data Bank ([2LJ5](https://www.rcsb.org/structure/2LJ5)). This ensemble is a set of 300 conformations which together best explain a set of Residual Dipolar Coupling data obtained from experiments. Imagined that you can get the same data from these hypothetical Ubq mutants, this 2LJ5 ensemble can provide a baseline to compare how the tail behave.

{{% notice note %}}
Although not necessary to follow this tutorial, you should check [the paper describing how this ensemble was obtained](https://link.springer.com/article/10.1007%2Fs10858-012-9644-3).
{{% /notice %}}

---

## The common approach

The common approach for this particular problem could be align the conformations and compute the RMSF (Root Mean Square Fluctuation). This will give you some number and you would be able to say something like "the C-terminal tail presents X angstroms of RMSF therefore ...", if X is higher than, let's say, 3 angstroms you would conclude that is flexible and use this number as a base line and compare with new data. Note that this hypothetical analyses scenario relies heavily on the decision made on how to superimpose the structure. For instance, if only the first three residues of the tail were used for the alignment and one just rely on the values of RMSF to judge flexibility, RMSF would suggest that the whole protein is very flexible with the exception of those 3 residues. Of course, this is an absurd example and only someone that does not understand what the RMSF quantity means would came to such conclusions, but you would be surprise on how often similar misinterpretation can happen on less obvious cases.

Imagined that you try different superposition solution for this Ubq C-terminal tail, but you are not confident that those RMSFs values are meaningful. Then you realize you will have to compare it with new data for the mutations and small differences in the superposition solution could be a problem during the interpretation. This problem is true for atomic coordinates, but there is also the possibility of use $\phi-\psi$ angles or define some set of collective variables. Each of those options have some limitations, some of them were discussed in the [FleXgeo paper](https://onlinelibrary.wiley.com/doi/10.1002/prot.25652), but for this tutorial let's assume you try those and for some reason did not trust the results. Maybe you are not sure if your collective variables are capturing the fundamental dynamics aspect, the periodicity of $\phi-\psi$ are making things more complicated in the data analyses or you simply would like to look at your data from a different perspective analyses. Like any normal regular human being, you find yourself thinking during the day:

> "**The world would be much better if we have an intuitive mathematical representation of the protein conformational space**".

Some friend told you about hearing some crazy rumour about some ancient protein differential geometry witchcraft that avoid the structural superposition problem. You google a bit, you check some awesome papers describing it and find out that this mathematical representation may help you solve your problem. Then you find that there is this FleXgeo software you can use to compute it and is convinced that you should at least give it a try.

---

## What is the logic behind this DG representation?

The rationale behind DG-representation implemented on FleXgeo is quite simple:

1. One can represent protein backbones as regular 3D spatial curves
2. Regular 3D patial curves can be uniquely characterized by curvature, $\kappa$, and torsion, $\tau$ as a function of arc-length, $s$
3. $\kappa$ and $\tau$ can be used to compare regular 3D spatial curves.

Considering 1), 2) and 3), therefore

> **Protein backbones can be compared solely based on $\kappa$ and $\tau$ values.**

---

## How this DG witchcraft avoids the superposition problem?

In a nutshell, the DG-based representation of protein backbone have the advantage of avoiding the superposition problem because the descriptors are absolute in space. This specific property rely on the [**Fundamental Theorem of Space Curves**](https://en.wikipedia.org/wiki/Fundamental_theorem_of_curves), which state that every regular spatial 3D-curve can be uniquely characterized by its curvature, $\kappa$, and $\tau$ as a function of arc length, $s$. **The mathematical proof of this theorem is not trivial, however its meaning is intuitive**. Imagine that one have two equal semi-rigid straight wires. Only two kind of distortions are possible to be imposed on such wires, 1) to curve it and/or 2) to torsion it in a given set of points. If wire $A$ get a specific sequence of distortions operations and this exact same operations is also applied to wire $B$, both wires will end up with the exact same final shape. Therefore, one could compare such wires just by analysing the specific set of distortion applied to each one, without the need to *superimpose* such wires.

Another way to look into this representation is to think how geometry tends to represent shapes using the minimum amount of descriptors as possible. For instance, circles can be describe solely by its radius, if two circles have different radius you know which one is bigger than the other without the need to superimposition. Similarly, 3D spatial curves can be uniquely specified by $\kappa$ and $\tau$ as a function of $s$. Now that you have a general notion of what this representation is all about, let's define our goals.

{{% notice note %}}
A more detailed description of the math behind the method is available at [FleXgeo paper](https://onlinelibrary.wiley.com/doi/10.1002/prot.25652), but a section devoted for the math-hardcore structural biologist (that we know you are) will be added to the website in the future.
{{% /notice %}}

---

## Main goal

Characterize and explore backbone dynamics of the C-terminal tail of Ubiquitin using differential geometry.

---

## Specific goals

1. Compute differential geometry representation
2. Plot the raw data
3. Compute $d_{max}$ to quantify protein flexibility
4. Check if there is an interesting clustering solution (SPOILER ALERT: there is not, but is nice to know how to do it)
