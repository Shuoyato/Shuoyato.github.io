---
layout:     post
title:      反问题
subtitle:   
date:       2023-12-10
author:     Shuo
header-img: img/evans.pjpg
catalog:   true
tags:
    - PDE
---

# Inverse Problems

Based on my 23 winter semester course Inverse Problems at WWU, and other lecture notes online. 

You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/) or [MathJax Plugin for Github](https://chrome.google.com/webstore/detail/mathjax-plugin-for-github/ioemnmodlmafdkllaclgeombjnmnbima?hl=en)

## Chapter 1 Introduction

Forward problem: Given known causes, determine the effects. 

Inverse problem: Observing the effects, recover the cause. 

Let $A:X\to Y$ denotes an operator that maps from a cause space $X$ to a effect space $Y$, computing a solution to the operator equation $Ax=y$ is not easy for three reasons: 

> 1, a solution may not exist,
> 
> 2, if it exists it may not be unique,
> 
> 3, small errors (noise) may get heavily amplified.

In the sense of Hadamard, the problem is called well-posed iff these three conditions are satisfied, i.e.,

> 1, for all $y\in Y$, there exists a $x\in X$ with $Ax=y$,
>
> 2, if $z\neq x$, then $Az\neq y$,
>
> 3, for all $x_k$ with $k\in\mathbb{N}$ with $Ax_k\to y$ implies $x_k\to x$.

Consider
> true solution $\hat{x}\in X$,
> exact measurements $\hat{y} = A\hat{x}\in Y$,
> noisy measurements $y^{\delta}\in Y$, such that $||y^{\delta}-y||\leq\delta$.

Given exact measurements $\hat{y}$, we could calculate $\hat{x} = A^{−1}\hat{y}$.
But how can we approximate $\hat{x}$ from noisy measurements $y^{\delta}$?

#### Tikhonov regularization: The inverse problem is replaced with 

> $x_{\alpha}=\arg\min ||Ax-y^{\delta}||^2+\alpha||x||^2$, with regularization parameter $\alpha$. 

Also we have that if $X, Y$ are Hilbert spaces, and $A$ is linear continuous, then the Tikhonov regularization is well-posed. 

## Chapter 2 Illustration via integration/differentiation

KATRIN is a German acronym (Karlsruhe Tritium Neutrino Experiment) for an undertaking to measure the mass of the electron antineutrino with sub-eV precision by examining the spectrum of electrons emitted from the beta decay of tritium. The experiment is a recognized CERN experiment (RE14).[1][2] The core of the apparatus is a 200-ton spectrometer.

Forward problem: $X=Y=L^2((0,1)), Ax=(s\mapsto \int^s_0 x(t)dt)$ 

#### Non-wellposedness of differentiation

> Consider the inverse problem $Ax=y$,\\
> In general it has no solution,\\
> If a solution exists, it is unique,\\
> but not continuous in $y\in Y$. 
