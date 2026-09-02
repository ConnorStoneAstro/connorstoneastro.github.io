---
title: "Caustics"
date: 2024-06-22
draft: false
tags: ["gravitational lensing", "software", "GPU", "simulation"]
summary: "Caustics is a GPU-accelerated Python package for strong gravitational lensing forward modelling, enabling fast simulation and inference for large-scale lensing surveys."
cover:
  image: /images/caustics_demo.png
  alt: "Example using the online caustics demo platform to distort the caustics logo."
  relative: false
  hidden: false
---

Strong gravitational lensing is a powerful probe of dark matter and cosmology, but modelling the large samples expected from upcoming surveys like Rubin/LSST requires fast, differentiable simulators. Caustics provides GPU-accelerated lensing forward models with automatic differentiation, enabling gradient-based inference at scale.

[GitHub](https://github.com/Ciela-Institute/caustics) · [Docs](https://caustics.readthedocs.io) · [Paper](https://joss.theoj.org/papers/10.21105/joss.07081)