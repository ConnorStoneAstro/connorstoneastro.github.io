---
title: "Simulation Based Inference"
date: 2024-01-01
summary: "An introduction to likelihood-free inference: what it is, why you'd use it, and how the four main approaches (NLE, NPE, NJE, NRE) work."
tags: ["statistics", "machine learning", "inference"]
math: true
---

## Setup

Simulation Based Inference (SBI) is what it says on the box, attempting to infer something about the world primarily through simulations.
It is also sometimes called Likelihood Free Inference (LFI) though this is somewhat misleading, since we do have access to the likelihood just not the density; a sampler is an expression of the likelihood though in a somewhat inconvenient format.

Ok, lets be more specific: our goal is to infer a posterior probability distribution $P(\theta | X)$ over parameters given some data where $\theta$ is the parameters and $X$ is the data.
Typically, what we have access to is a prior $P(\theta)$ over the parameters (if you think you don't have this, I assure you that you do) and a likelihood $P(X | \theta)$.
Those two parts describe how our data came about through a two step process:

1. Sample parameters $\theta_i \sim P(\theta)$
2. Sample the data $X_i \sim P(X | \theta_i)$

The goal of SBI is to infer the posterior on $\theta$ given some data $X$ and the two sampling functions above, under the restriction that we can't evaluate the probability densities of those functions (or at least not the likelihood).

There are broadly three reasons you would want to use SBI:

1. **You can't evaluate your likelihood.** This is the core motivation — it comes from very complex simulators that include as much realism as possible.
2. **Your likelihood is very slow to evaluate.** Costly integrals, gigantic matrix inversions, or other compute-heavy operations that are impractical to run thousands of times.
3. **Large or trans-dimensional nuisance parameters.** SBI can marginalise over nuisance parameters preemptively, though this bakes in a prior for them.

## The four approaches

There are broadly four approaches used in the community: Neural Likelihood Estimation (NLE), Neural Posterior Estimation (NPE), Neural Joint Estimation (NJE), and Neural Ratio Estimation (NRE).
(The "Neural" part is just an implementation detail — it would be dropped tomorrow if something better than neural networks came along.)

![Comparison of different SBI target distributions](/images/demos/SBIdemo.png)
*Figure 1: Comparison of the different SBI target distributions. The interplay of the likelihood, prior, and different normalization directions in a simple inference task.*

- **NLE** (top left) approximates the likelihood density directly. Independent of the prior, and often simpler than the alternatives.
- **NPE** (top right) fits a posterior density function — enter your data $X$ and get $P(\theta|X)$ out. The most direct approach.
- **NJE** (bottom left) works in the full joint space of $\theta$ and $X$, which makes density estimation hard. Least commonly used.
- **NRE** (bottom right) trains a classifier to distinguish real joint samples from marginal ones. Easier to train, lets the prior do more work.

NPE, NJE, and NRE all bake the prior into their distribution, making it difficult to change the prior after training. NLE avoids this and is compatible with active learning.

## Example: photometric redshifts

A great real-world example is photometric redshift estimation.
It is straightforward to determine the redshift of a galaxy from a high-resolution spectrum, but often all we have is a few wide integrated photometric bands.
As shown in Figure 2, a variety of algorithms can recover photo-z estimates, but with notable scatter.

![RAIL paper comparison of photometric redshift estimation algorithms](/images/demos/photoz_specz.png)
*Figure 2: Comparison of photometric redshift estimation algorithms. Estimated redshift (y-axis) vs reference redshift (x-axis). From [Zhang et al. 2025](https://ui.adsabs.harvard.edu/abs/2025arXiv251007370Z/abstract).*

The scatter isn't a simple Gaussian — the 2D histograms in Figure 2 essentially provide the (N)LE or (N)PE depending on normalisation.
For this problem, a neural network is overkill; the classical histogram already captures the information structure.

## Some math

For NLE/NPE/NJE, the training objective is to minimise the KL divergence between the network's density $P(X|\theta, w)$ and the true likelihood:

$$D_{KL} = \int P(X_i|\theta)\ln\left(\frac{P(X_i|\theta,w)}{P(X_i|\theta)}\right)dX_i$$

Monte-Carlo estimation lets us approximate this by sampling from $P(X|\theta)$:

$$D_{KL} \approx \frac{1}{N}\sum_{X_i\sim P(X_i|\theta)}\ln\left(\frac{P(X_i|\theta,w)}{P(X_i|\theta)}\right)$$

Taking the gradient $\nabla_w D_{KL}$ removes the dependence on the true likelihood entirely — we can minimise the KL divergence without ever evaluating it directly.

For NRE, a binary cross-entropy classifier distinguishes joint samples $\{\theta, X\}$ from marginal pairs $\{\theta', X'\}$. In the limit of many examples, it learns:

$$r(\theta, X) = \frac{P(\theta, X)}{P(\theta)P(X)}$$

The posterior then follows as $r(\theta, X) P(\theta)$, from the chain rule of probability.

Finally, these distributions can also be trained using [score matching](https://arxiv.org/abs/2011.13456) — focusing on annealed versions of the PDF which can be easier to model, at some cost to accuracy on the true distribution.
