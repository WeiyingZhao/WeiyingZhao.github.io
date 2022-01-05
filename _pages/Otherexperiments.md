---
layout: archive
# title: "Semantic segmentation based heterogeneous images change detection"
permalink: /Otherexperiments/
author_profile: true
---


{% include base_path %}

# 1. Univariate time series missing value imputation

Optical remote sensing images are easily affected by the cloudy weather, which lead to missing or smaller NDVI values. We propose to combine the Savitzky–Golay filter and ‘smoothn’ method to obtain the missing NDVI values.  As can be seen from the following figure,  the smoothed Savitzky–Golay filter method can handle missing values and can provide good results in the tail area. However, when all the maximum NDVI values on the peak area are lost, the interpolation result may have a large bias.

![S2NDVI_smooth](/images/S2NDVI_smooth.png)

Figure 1. Time series Sentinel-2 NDVI smooth


# 2. Multivariate time series missing value imputation

When some important features of the time series NDVI are lost, the interpolation method may not be able to restore the true value. We propose to use attention-based BiLSTM to forecast the NDVI values. The historical multisensor data acquired over the study area will be used to train the model. The architecture of the model is shown in Figure 2.

![Attention_BiLSTM](/images/Attention_BiLSTM.png)

Figure 2. Attention-Based BiLSTM Networks for NDVI estimation

In this method, the CNN is used to extract deep features from the time‐series signal as an input, and then the BiLSTM network with a symmetric structure is constructed to learn the time‐series information between the feature vectors. The attention mechanism is introduced to self‐adaptively perceive the network weights associated with the forecasting results and distribute the weights reasonably. 