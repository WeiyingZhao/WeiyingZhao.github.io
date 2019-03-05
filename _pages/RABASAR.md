---
layout: archive
title: "RABASAR: A fast ratio based multi-temporal SAR despeckling"
permalink: /RABASAR/
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

The interest of ratio image 
---
  * In case of temporally stable area and ENL of the super-image infinite
   
	ratio image = pure Gamma noise of mean 1

  * In case of  a limited ENL and temporal variations
   
	Fisher pdf that can be approximated by Gamma pdf

In all situations, ratio image with fewer structures and variations than an original SAR image  
→   Easier to denoise !



Experimental results
======
   * 31 Sentinel-1 images which are downloaded from [Sentinel open access hub](https://sentinels.copernicus.eu/web/sentinel/sentinel-data-access) are used.

   * MuLog-BM3D method is used to denoise the super-image which is acquired through temporal averaging. 

![NoisySuperImg](/images/NoisySuperImg1.png)
Figure 2. Noisy image and MuLog-BM3D denoised super-image.

![DNoisyImg](/images/DNoisyImg1.png)

Figure 3. RABASAR denoised image

	






  
References
======

[1] Deledalle, C.A., Denis, L., Tabti, S. and Tupin, F., 2017. MuLoG, or How to apply Gaussian denoisers to multi-channel SAR speckle reduction?. IEEE Transactions on Image Processing, 26(9), pp.4389-4403.

[2] Zhao, W., Deledalle, C.A., Denis, L., Maître, H., Nicolas, J.M. and Tupin, F., 2018, July. RABASAR: A FAST RATIO BASED MULTI-TEMPORAL SAR DESPECKLING. In IEEE International Geoscience and Remote Sensing Symposium, IGARSS 2018.

[3] Zhao, W., Denis, L., Deledalle, C.A., Maître, H., Nicolas, J-M. and Tupin, F. Ratio-Based Multitemporal SAR Images Denoising: RABASAR. IEEE Transactions on Geoscience and Remote Sensing. 2019.




Code links
======
[MuLog-BM3D](https://www.math.u-bordeaux.fr/~cdeledal/mulog.php): https://www.math.u-bordeaux.fr/~cdeledal/mulog.php

[RABASAR](https://bitbucket.org/cdeledalle/rabasar) https://bitbucket.org/cdeledalle/rabasar
  

