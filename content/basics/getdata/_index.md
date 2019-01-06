+++
title = "Define analyses objectives"
date = 2018-12-29T17:44:21+01:00
weight = 6
#chapter = true
pre = "<b>1.2 </b>"
+++

On this basic tutorial, we will reproduce the analyses of the Ubiquitin ensemble presented at FleXgeo paper. The Ubiquitin (Ubq) is a good example of a **regular rigid globular protein with a very flexible N-terminal tail**. This is a fairly simple and common analyses scenario on protein structural biology projects, therefore a good place to start. As on any data analyses scenario, before we start to do anything at all let's define as objectively as possible our questions and goals.

---

## What we want to know?

Flexibility is an important aspect of protein function and let's assume that for some reason you are interest on Ubq N-terminal tail dynamics.
Maybe you found experimental evidence that mutations on this region affects Ubq binding capabilities and want to know how flexible it actually is and which residues are more important.

---

## What data do we have?

Fortunately, there is an Ubq conformational ensemble determined based on NMR-restrained metadynamics available at Protein Data Bank ([2LJ5](https://www.rcsb.org/structure/2LJ5)). This ensemble is composed of 300 conformations which best fit the Residual Dipolar Coupling data obtained. This data can provide a baseline to compare how the tail behave under 

{{% notice note %}}
Although not necessary to follow this tutorial, but you should check [the paper describing how this ensemble was obtained](https://link.springer.com/article/10.1007%2Fs10858-012-9644-3)

{{% /notice %}}

---

## Why use differential geometry?

This is an common scenario in which the decision of how to superimpose the structure is crucial to the measurements. Of course this is true for atomic coordinates, but there is also the possibility of use $\phi-\psi$ angles or define some set of collective variables. But for the porpouse of this tutorial, let's assume you try those and for some reason did not trust the results. Maybe you are not sure if your collective variables are capturing every dynamics aspect you need, or the periodicity of $\phi-\psi$ are making things more complicated in the data analyses. So do you wonder if it would be nice to have an intuitive mathematical representation of the protein conformational space, some friend told you about the advantages of DG representation, you checked a awesome paper describing it and found that there is this FleXgeo software you can use to compute and is convinced that you should at least give it a try. So you define your goals.

---

## Main goal

Our main goal is to characterize backbone dynamics of the C-terminal tail of Ubiquitin using differential geometry.

---

## Specific goals

1. Compute differential geometry representation
2. Plot the raw data
3. Compute $d_{max}$ to quantify protein flexibility
4. Check if there is an interesting clustering solution (well, just because is nice to know how to do).
