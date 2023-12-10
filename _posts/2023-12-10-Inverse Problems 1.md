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

> Consider the inverse problem $Ax=y$,
> 
> In general it has no solution, (if $y\notin W^{1,2}((0,1))$, then it has no weak derivative in $X$),
>  
> If a solution exists, it is unique, (because $x(s)=y'(s)$ and the weak derivative is unique), 
> 
> but not continuous in $y\in Y$. 

#### Tikhonov regularization: 

> $x_{\alpha}=\arg\min \int^1_0|\int^s_0x(t)dt-y^{\delta}(s)|^2+\alpha\int^1_0|x(t)|^2dt$,
>
> Set $y_{\alpha}=Ax_{\alpha}$, then $y_{\alpha}$ solves $-\alpha y''_ {\alpha}+y_{\alpha}-y^{\delta}=0$ on $(0,1)$ and $y_{\alpha}(0)=0, y'_{\alpha}(1)=0$.
>
> thus $y_{\alpha}$ is the solution of an implicit Euler step with stepsize $\alpha$ of the heat equation with homogeneous Dirichlet-/Neumann-boundary conditions.
>  $y^{\delta}$ first is smoothed to $y_{\alpha}$!

#### Recall Sobolev space

> Assume that $\Omega$ is an open subset of $\mathbb{R}^n$.
>
> The Sobolev space $W^{k, p}(\Omega)$ consists of functions $u \in L^p(\Omega)$ such that for every multi-index $\alpha$ with $|\alpha| \leq k$, the weak derivative $D^\alpha u$ exists and $D^\alpha u \in L^p(\Omega)$.
>
> Thus $W^{k, p}(\Omega)=\{ u \in L^p(\Omega): D^\alpha u \in L^p(\Omega),|\alpha| \leq k \} $ .

## Chapter 3 Some classical inverse/forward problems

> 1, differentiation/integration
>
> 2, X-ray transform
