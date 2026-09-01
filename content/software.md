---
title: "Software"
url: "/software/"
summary: "Open-source scientific software by Connor Stone"
description: "GPU-accelerated tools for astronomical image analysis, gravitational lensing, and scientific simulation"
cover:
  image: /images/caskade_graph.png
  alt: "caskade computational graph visualization"
  relative: false
  hidden: false
---

I develop open-source scientific software for the astronomy community. All projects are freely available on GitHub.

## Caustics

<!-- SECTION IMAGE — replace src with your own -->
<img class="section-img" src="/images/hero.jpg" alt="Caustics — gravitational lensing simulations">

Fast, differentiable strong gravitational lensing simulations in Python. Built on PyTorch for GPU acceleration and automatic differentiation, enabling large-scale lensing inference.

[GitHub](https://github.com/Ciela-Institute/caustics) · [Docs](https://caustics.readthedocs.io) · [Paper](https://ui.adsabs.harvard.edu/abs/2024JOSS....9.6080S/abstract)

---

## AstroPhot

<!-- SECTION IMAGE — replace src with your own -->
<img class="section-img" src="/images/m51.jpg" alt="AstroPhot — galaxy photometric fitting">

A GPU-accelerated tool for fitting complex astronomical images. AstroPhot provides a large zoo of parametric models for stars, galaxies, and other sources, combinable to represent arbitrarily complex scenes. Key features:

- **GPU acceleration** — roughly an order of magnitude speedup; hardware is auto-detected
- **Multi-band fitting** — simultaneously models multiple images, epochs, and wavelength bands
- **SED extraction** — broadband spectral energy distributions via forward modelling, with no need for aperture corrections or PSF matching
- **Crowded fields** — handles large models with many overlapping objects
- **Uncertainty analysis** — built-in support for MCMC and Levenberg-Marquardt optimisers, with simultaneous PSF parameter optimisation

[GitHub](https://github.com/ConnorStoneAstro/AstroPhot) · [Docs](https://astrophot.readthedocs.io)

---

## AutoProf

<!-- SECTION IMAGE — replace src with your own -->
<img class="section-img" src="/images/m51.jpg" alt="AutoProf — non-parametric galaxy profiles">

A pipeline for non-parametric galaxy image analysis, emphasising rapid implementation without sacrificing flexibility. Capabilities include PSF star identification, ellipse fitting, radial profile extraction, residual and model generation, and background analysis.

[GitHub](https://github.com/ConnorStoneAstro/AutoProf) · [Docs](https://autoprof.readthedocs.io) · [Paper](https://ui.adsabs.harvard.edu/abs/2021arXiv210613809S/abstract)

---

## caskade

<!-- SECTION IMAGE — replace src with your own -->
<img class="section-img" src="/images/caskade_graph.png" alt="caskade — computational graph">

A framework for building modular, composable scientific simulators in Python. Designed to reduce boilerplate and make research pipelines easier to write, test, and refactor.

[GitHub](https://github.com/ConnorStoneAstro/caskade) · [Paper](https://ui.adsabs.harvard.edu/abs/2025arXiv251007370Z/abstract)
