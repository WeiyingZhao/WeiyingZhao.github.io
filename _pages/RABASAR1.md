---
layout: archive
title: "RABASAR: A fast ratio based multi-temporal SAR despeckling"
permalink: /RABASAR1/
author_profile: true
---

{% include base_path %}

### This work has been done in collaboration with [Loïc Denis](https://perso.univ-st-etienne.fr/deniloic/), [Charles-Alban Deledalle](https://www.math.u-bordeaux.fr/~cdeledal/), [Henri Maître](https://perso.telecom-paristech.fr/maitre/), [Jean-Marie Nicolas](https://perso.telecom-paristech.fr/nicolas/) and [Florence Tupin](https://perso.telecom-paristech.fr/tupin/).

The principle of the proposed method
======
The proposed approach can be divided into three steps: 

   * calculation of the “super-image” through temporal averaging; 
    
   * denoising the ratio images formed through dividing the noisy images by the “super-image”; 
    
   * computing denoised images by multiplying the denoised ratio images with the “super-image”.

Thanks to the spatial stationarity improvement in the ratio images, denoising these ratio images with a speckle-reduction
method is more effective than denoising the original multitemporal stack. The data volume to be processed is also reduced compared to other methods through the use of the “super-image”.

![Flowchart](/images/flowchart2.png)
Figure 1. Multi-temporal SAR image denoising framework
