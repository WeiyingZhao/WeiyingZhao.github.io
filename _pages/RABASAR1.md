---
layout: archive
title: "RABASAR: A fast ratio based multi-temporal SAR despeckling"
permalink: /RABASAR1/
author_profile: true
---

{% include base_path %}

The evaluation method proposed here follows the idea presented in [Riot et al., 2017]
which examines the residual image and looks for possible remaining structural elements
in this residual image. Instead of using autocorrelation, we used patch base autocovariance method during the residual evaluation.
Unlike maximum ENL estimation or αβ estimation [Gomez
et al., 2016] method, this method is automatic and does not rely on a supervised
selection of homogeneous regions. It also provides a global score for the whole image.


![changeAreaDetection](/images/residualEvaluation1.jpg)

Figure 1. Denoising real Sentinel-1 images over the region of Saclay (the original noisy
image is available in figure 6.2(a)). Left column : denoised results ; middle column : residual
ratio images ; right column : residuals evaluation results with displaying value range [0, 4].
64 Sentinel-1 images are used.
