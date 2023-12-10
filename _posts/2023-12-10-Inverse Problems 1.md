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
> 3. for all $x_k$ with $k\in\mathbb{N}$ with $Ax_k\to y$ implies $x_k\to x$.

Tikhonov regularization: The inverse problem is replaced with 

> $x_{\alpha}=\arg\min ||Ax-y||^2+\alpha||X||^2$.




