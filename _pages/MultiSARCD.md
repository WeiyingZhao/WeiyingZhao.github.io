---
layout: archive
title: "Multitemporal SAR images change detection"
permalink: /MultiSARCD/
author_profile: true
---


{% include base_path %}

To mining different change profiles, we propose several methods to detect the changed area, change magnitude, change classes and changed time. 

This work is suppervised by [Florence Tupin](https://perso.telecom-paristech.fr/tupin/) and [Henri Maître](https://perso.telecom-paristech.fr/maitre/).

# 1. Change area detection



Based on RABASAR provided data which have spatial varying ENL, we propose a simplified generalized log-likelihood ratio test (SGLR) method assuming that corresponding temporal pixels have the same equivalent number of looks (ENL). During the test, chi-squared distributed probability function is utilized to theoretically define the false alarm rate. 


![changeAreaDetection](/images/changeAreaDetection.png)

Figure 1. Sendai SAR image pair change detection comparison. (a) noisy image acquired in 06/05/2011, (b) noisy image acquired in  08/06/2011, (c) optical image acquired in 06/04/2011, (d) RGB combination of the noisy images, (e) MIMOSA detection results with a priori FAR equal to 1%, (f) CGLRT detection results with 2SPPB  data, (g) SGLR detection results with RABASAR-DAM  data, (h) SGLR detection results with RABASAR-DBWAM  data.


# 2. Change magnitude detection

## 2.1 Method introduction

## 2.2 Experimental results

![changeMagnitudeDetection](/images/changeMagnitudeDetection.png)



# 3. Change classification

## 3.1 Method introduction

## 3.2 Experimental results

![changeClassification](/images/changeClassification.png)


# 4. Change time detection

## 4.1 Method introduction

## 4.2 Experimental results

![changeTimeDetection](/images/changeTimeDetection.png)






