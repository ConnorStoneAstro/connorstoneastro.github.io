---
title: "PTED"
date: 2025-11-09
draft: false
tags: ["software", "simulation", "Python", "scientific computing"]
summary: "The Permutation Test using the Energy Distance (PTED) is a powerful multi-dimensional two sample test."
cover:
  image: /images/pted.png
  alt: "Visualization of the process for using PTED."
  relative: false
  hidden: false
---

PTED (pronounced "ted") takes in x and y two datasets and determines if they were sampled from the same underlying distribution. It produces a p-value under the null hypothesis that they are sampled from the same distribution. The samples may be multi-dimensional, and the p-value is "exact" meaning it has a correctly calibrated type I error rate regardless of the data distribution.

[GitHub](https://github.com/ConnorStoneAstro/pted)