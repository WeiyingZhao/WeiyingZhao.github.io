---
layout: archive
title: "RABASAR: A fast ratio based multi-temporal SAR despeckling"
permalink: /oscd/
author_profile: true
---

{% include base_path %}

This work is cooperated with [Loïc Denis](https://perso.univ-st-etienne.fr/deniloic/), [Charles-Alban Deledalle](https://www.math.u-bordeaux.fr/~cdeledal/), [Henri Maître](https://perso.telecom-paristech.fr/maitre/), [Jean-Marie Nicolas](https://perso.telecom-paristech.fr/nicolas/) and [Florence Tupin](https://perso.telecom-paristech.fr/tupin/).

Principle of the proposed method
======
The proposed approach can be divided into three steps: 

    1)calculation of the “super-image” through temporal averaging; 
    
    2)denoising the ratio images formed through dividing the noisy images by the “super-image”; 
    
    3)computing denoised images by multiplying the denoised ratio images with the “super-image”.

Thanks to the spatial stationarity improvement in the ratio images, denoising these ratio images with a speckle-reduction
method is more effective than denoising the original multitemporal stack. The data volume to be processed is also reduced compared to other methods through the use of the “superimage”.

![Flowchart](/images/flowchart2.png)
Figure 1. Multi-temporal SAR image denoising framework


Experimental results
======

MuLog-BM3D method is used to denoise the super-image which is acquired through temporal averaging 31 Sentinel-1 images. 

![NoisySuperImg](/images/NoisySuperImg.png)
Figure 2. Noisy image and denoised super-image.

![DNoisyImg](/images/DNoisyImg.png)
Figure 3. Denoised image

	




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
  

