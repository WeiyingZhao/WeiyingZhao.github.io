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

# 3. Multi-location multi-sensor time series missing value imputation

When the soil moisture sensor is disconnected from the server, we may lose a large amount of time series data, resulting in the loss of spatial soil moisture variance. Given the history of soil moisture data measured nearby, we successfully applied a GNN-LSTM network to impute missing values.

![Attention_BiLSTM](/images/GNN_flowchart.png)

Figure 3. Geolocation of different sensors measuring the same information at same time steps. 
(a) The blue sensors indicate the sensors close to the central sensor. (b) We obtain the spatial features by
obtaining the topological relationship among the sensor 1 and its surrounding sensors [1]

In the future, we are going to add multisensor information to the model to include the spatial variance.

[1]Zhao, L., Song, Y., Zhang, C., Liu, Y., Wang, P., Lin, T., Deng, M. and Li, H., 2019. T-gcn: A temporal graph convolutional network for traffic prediction. IEEE Transactions on Intelligent Transportation Systems, 21(9), pp.3848-3858.

[2]Yu, B., Yin, H. and Zhu, Z., 2017. Spatio-temporal graph convolutional networks: A deep learning framework for traffic forecasting. arXiv preprint arXiv:1709.04875.
