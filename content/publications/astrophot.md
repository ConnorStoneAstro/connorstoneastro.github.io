---
title: "💻 AstroPhot: Fitting Everything Everywhere All at Once in Astronomical Images"
date: 2023-08-03
draft: false
tags: ["photometry", "software", "machine learning", "galaxies"]
summary: "AstroPhot is a Python package for simultaneous multi-band, multi-object photometric fitting of astronomical images using automatic differentiation and GPU acceleration."
cover:
  image: /images/AstroPhot_multiband.png
  alt: "A multi-band, multi-object fitting example with AstroPhot. Fitting seven bands from UV to IR, showing the data, model, and residuals."
  relative: false
  hidden: false
---

**Authors:** Connor Stone, Stephane Courteau, Jean-Charles Cuillandre, Yashar Hezaveh, Laurence Perreault-Levasseur, Nikhil Arora

**arXiv:** [2308.01957](https://arxiv.org/abs/2308.01957)  
**Journal:** Monthly Notices of the Royal Astronomical Society  
**DOI:** [10.1093/mnras/stad2477](https://doi.org/10.1093/mnras/stad2477)

**Website:** [AstroPhot](https://astrophot.readthedocs.io/en/latest/)  
**GitHub:** [Autostronomy/AstroPhot](https://github.com/Autostronomy/AstroPhot)

---

Galaxy photometry underlies virtually all extragalactic science, yet existing tools are limited to single-band fitting with hand-tuned workflows. AstroPhot is a flexible tool for jointly fitting many sources in an image simultaneously across multiple bands, leveraging automatic differentiation (PyTorch/JAX) and GPU acceleration to make previously intractable analyses easy to set up.
