---
layout: archive
title: "RABASAR: A fast ratio based multi-temporal sar despeckling"
permalink: /oscd/
author_profile: true
---

{% include base_path %}

The Dataset
======
The Onera Satellite Change Detection dataset addresses the issue of detecting changes between satellite images from different dates.

It comprises 24 pairs of multispectral images taken from the [Sentinel-2 satellites](https://sentinel.esa.int/web/sentinel/missions/sentinel-2) between 2015 and 2018. Locations are picked all over the world, in Brazil, USA, Europe, Middle-East and Asia. For each location, registered pairs of 13-band multispectral satellite images obtained by the Sentinel-2 satellites are provided. Images vary in spatial resolution between 10m, 20m and 60m.

Pixel-level change ground truth is provided for 14 of the image pairs. The annotated changes focus on urban changes, such as new buildings or new roads. These data can be used for training and setting parameters of change detection algorithms.

![Beirut images](/images/beirut-conc.png)
Example: "beirut" image pair and associated change map.

The Benchmark
======
The algorithms can be tested in a benchmark for change detection.

The ground truth for the 10 remaining images remain undisclosed. Change prediction maps can be uploaded for evaluation on the [IEEE GRSS DASE website](http://dase.ticinumaerospace.com/). Various metrics such as per-class accuracy and confusion matrices are automatically computed on the website, and are available for participants. Comparison to the best performing methods is provided in the leaderboard associated with this benchmark.
  
References
======
If you use this work for your projects, please take the time to cite our paper:

[*Urban Change Detection for Multispectral Earth Observation Using Convolutional Neural Networks*, R. Caye Daudt, B. Le Saux, A. Boulch, Y. Gousseau. IEEE International Geoscience and Remote Sensing Symposium (IGARSS’2018). Valencia, Spain. July 2018.](https://rcdaudt.github.io/publication/2018-08-22-urban-change-detection)

[[PDF]](http://rcdaudt.github.io/files/2018igarss-change-detection.pdf) [[BibTeX]](http://rcdaudt.github.io/files/daudt2018urban.bib)


Links
======
You can find the dataset on IEEE GRSS DASE webpages:

* [http://dase.ticinumaerospace.com/](http://dase.ticinumaerospace.com/)
* [http://dase.grss-ieee.org/](http://dase.grss-ieee.org/)





The Team
======
* [Rodrigo Caye Daudt](https://rcdaudt.github.io/), rodrigo.daudt@onera.fr
* [Bertrand Le Saux](https://blesaux.github.io/), bertrand.le_saux@onera.fr
* [Alexandre Boulch](https://aboulch.github.io/), alexandre.boulch@onera.fr
* [Yann Gousseau](https://perso.telecom-paristech.fr/gousseau/), yann.gousseau@telecom-paristech.fr
  

