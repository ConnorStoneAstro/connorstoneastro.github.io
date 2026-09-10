---
title: "📄 Pixellated Posterior Sampling of Point Spread Functions in Astronomical Images"
date: 2025-11-26
draft: false
tags: ["machine learning", "PSF", "photometry", "Bayesian inference"]
summary: "A framework for fully probabilistic, pixel-level inference of the point spread function directly from astronomical images, enabling principled uncertainty quantification in downstream photometric analyses."
cover:
  image: /images/moneyplot.png
  alt: "Comparison of PSF reconstruction showing a cutout of a bright point source and four recovery methods at 4x resolution as well as their residuals."
  relative: false
  hidden: false
---

**Authors:** Connor Stone, Ronan Legin, Alexandre Adam, Nikolay Malkin, Gabriel Missael Barco, Laurence Perreault-Levasseur, Yashar Hezaveh

**arXiv:** [2511.19594](https://arxiv.org/abs/2511.19594)

---

We present a method for pixellated posterior sampling of the PSF in astronomical images. Rather than estimating a single best-fit PSF, we infer the full posterior distribution over possible PSF profiles, propagating PSF uncertainty into all downstream measurements. This is essential for weak-lensing shape measurements, deconvolution, and any analysis where PSF mischaracterisation is a dominant systematic.
