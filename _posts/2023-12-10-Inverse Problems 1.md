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

Let $K:U\to V$ denotes an operator that maps from a cause space $U$ to a effect space $V$, computing a solution to the operator equation $Ku=f$ is not easy for three reasons: 

> 1, a solution may not exist,
> 
> 2, if it exists it may not be unique,
> 
> 3, small errors (noise) may get heavily amplified.

In the sense of Hadamard, the problem is called well-posed iff these three conditions are satisfied, i.e.,

> for all $f\in V$, there exists a $u\in U$ with $Ku=f$,
>
> if $u\neq v$, then $Kv\neq f$,
>
> for all $\{u_k\}_{k\in\mathbb{N}}$ with $Ku_k\to f$ implies $u_k\to u$. 


