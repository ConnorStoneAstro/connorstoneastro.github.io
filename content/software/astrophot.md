---
title: "AstroPhot"
date: 2023-08-03
draft: false
tags: ["photometry", "software", "machine learning", "galaxies"]
summary: "AstroPhot is a Python package for simultaneous multi-band, multi-object photometric fitting of astronomical images using automatic differentiation and GPU acceleration."
cover:
  image: /images/research/demo_astrophot_fit.png
  alt: "A multi-epoch, multi-object fitting example with AstroPhot. Fitting a mock supernova embedded in a galaxy with data, model, and residuals."
  relative: true
  hidden: false
---

Galaxy photometry underlies virtually all extragalactic science, yet many existing tools are limited to single-band fitting with hard to modify workflows. AstroPhot is a flexible tool for jointly fitting many sources in an image simultaneously across multiple bands/epochs, leveraging automatic differentiation and GPU acceleration (PyTorch/JAX) to make previously intractable analyses easy to set up. AstroPhot provides a large zoo of parametric models for stars, galaxies, and other sources, combinable to represent arbitrarily complex scenes. Key features:

- **GPU acceleration** — roughly an order of magnitude speedup; hardware is auto-detected
- **Multi-band fitting** — simultaneously models multiple images, epochs, and wavelength bands
- **SED extraction** — broadband spectral energy distributions via forward modelling, with no need for aperture corrections or PSF matching
- **Crowded fields** — handles large models with many overlapping objects
- **Simultaneous PSF fitting** — the PSF may be included as part of a model and optimized alongside other components
- **Uncertainty analysis** — built-in support for MCMC and Levenberg-Marquardt optimisers, with simultaneous PSF parameter optimisation

[GitHub](https://github.com/Autostronomy/AstroPhot) · [Docs](https://astrophot.readthedocs.io) · [Paper](https://doi.org/10.1093/mnras/stad2477)