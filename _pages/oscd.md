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

   * calculation of the “super-image” through temporal averaging; 
    
   * denoising the ratio images formed through dividing the noisy images by the “super-image”; 
    
   * computing denoised images by multiplying the denoised ratio images with the “super-image”.

Thanks to the spatial stationarity improvement in the ratio images, denoising these ratio images with a speckle-reduction
method is more effective than denoising the original multitemporal stack. The data volume to be processed is also reduced compared to other methods through the use of the “superimage”.

![Flowchart](/images/flowchart2.png)
Figure 1. Multi-temporal SAR image denoising framework

Interest of the ratio image 
---
   * In case of temporally stable area and ENL of the super-image infinite
   
	ratio image = pure Gamma noise of mean 1

   * In case of  a limited ENL and temporal variations
   
	Fisher pdf that can be approximated by Gamma pdf

In all situations, ratio image with less structures and variations than an original SAR image  
→   Easier to denoise !



Experimental results
======
   * 31 Sentinel-1 images which are downloaded from [Sentinel open access hub](https://sentinels.copernicus.eu/web/sentinel/sentinel-data-access) are used.

   * MuLog-BM3D method is used to denoise the super-image which is acquired through temporal averaging 31 Sentinel-1 images. 

![NoisySuperImg](/images/NoisySuperImg.png)
Figure 2. Noisy image and denoised super-image.

![DNoisyImg](/images/DNoisyImg1.png)

Figure 3. Denoised image (enlarged)

	






  
References
======

[*Urban Change Detection for Multispectral Earth Observation Using Convolutional Neural Networks*, R. Caye Daudt, B. Le Saux, A. Boulch, Y. Gousseau. IEEE International Geoscience and Remote Sensing Symposium (IGARSS’2018). Valencia, Spain. July 2018.](https://rcdaudt.github.io/publication/2018-08-22-urban-change-detection)

[[PDF]](http://rcdaudt.github.io/files/2018igarss-change-detection.pdf) [[BibTeX]](http://rcdaudt.github.io/files/daudt2018urban.bib)


Links
======

  

