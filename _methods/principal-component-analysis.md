---
title: "Principal Component Analysis (PCA)"
excerpt: "A linear dimensionality reduction method that finds the axes of maximum variance in high-dimensional data."
date: 2024-01-01
---

## What it is

PCA transforms a high-dimensional dataset into a smaller set of uncorrelated variables called *principal components* (PCs). Each PC is a linear combination of the original variables, ordered so that the first PC captures the most variance, the second captures the next most, and so on.

In neuroscience, it's commonly used to compress population activity (e.g. 100 neurons → 3 PCs) so we can visualize and analyze the geometry of neural responses.

## How it works

Given a data matrix **X** (observations × features), PCA:
1. Centers the data (subtracts the mean of each feature)
2. Computes the covariance matrix **C = XᵀX / (n−1)**
3. Finds the eigenvectors and eigenvalues of **C**
4. Projects data onto the top *k* eigenvectors

The eigenvectors are the principal components; the eigenvalues tell you how much variance each PC explains.

## When to use it

- Visualizing high-dimensional data in 2D or 3D
- Removing noise (by keeping only the top PCs)
- As a preprocessing step before clustering or regression
- Checking for structure in neural population activity

## Limitations

- Only captures *linear* structure — nonlinear manifolds require UMAP, t-SNE, or autoencoders
- Sensitive to scaling — features with larger variance dominate unless you standardize
- PCs may not correspond to interpretable dimensions

## Resources

- **Shlens (2014)** — "A Tutorial on Principal Component Analysis" — clear mathematical derivation
- **Cunningham & Yu (2014)** — "Dimensionality reduction for large-scale neural recordings" — neuroscience-specific framing
- [StatQuest: PCA clearly explained (YouTube)](https://www.youtube.com/watch?v=FgakZw6K1QQ)
