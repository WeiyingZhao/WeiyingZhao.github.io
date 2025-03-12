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

# 4. Wildfire monitoring with a simplified generalized likelihood ratio test

Recent wildfires can rapidly transform landscapes, creating extensive burned areas that evolve over time. In events such as the wildfire that swept through Ma On Shan, Hong Kong, timely and precise monitoring of both the spatial extent and temporal evolution of the burn scar is critical for guiding emergency response, ecological restoration, and long‐term land management efforts.

<div style="display: flex; justify-content: center; gap: 20px;">
  <figure style="margin: 0; text-align: center;">
    <img src="/images/wildfire_area.jpg" alt="Wildfire area" width="400" height="400">
  </figure>
  <figure style="margin: 0; text-align: center;">
    <img src="/images/Sentinel2_image.jpg" alt="Sentinel-2 image" width="400" height="400">
  </figure>
</div>

Figure 4. Wildfire monitoring with a simplified generalized likelihood ratio test over Ma On Shan, Hong Kong. Left: Wildfire area, Right: Sentinel-2 image acquired after the fire.

This method offers a promising solution for such challenges by leveraging multitemporal Synthetic Aperture Radar (SAR) imagery. Unlike optical sensors, SAR can image the surface regardless of cloud cover or smoke and it can penetrate the canopy, making it ideal for monitoring wildfires. The approach uses a denoising technique (RABASAR) to reduce speckle noise—a common challenge in SAR data—and applies a simplified generalized likelihood ratio (SGLR) test to detect changes between images acquired at different times. This not only helps delineate the change area (i.e. the burned region) but also estimates key change time parameters such as the start, maximum, and stop times of the change process. By integrating these capabilities, the method can produce a detailed, temporally resolved map of wildfire progression and recovery.

# 5. Detecting changes in aquaculture areas 

<div style="display: flex; justify-content: center; gap: 20px;">
  <figure style="margin: 0; text-align: center;">
    <img src="/images/water_area_change_monitoring.png" alt="water_area_change_monitoring" width="800" height="240">
  </figure>
</div>

Figure 5. Aquaculture area change detection using multitemporal SAR images. Left: Temporal average, Right: change time visualization results.

Detecting changes in aquaculture areas is crucial for ensuring environmental sustainability and effective management. It helps monitor water quality, sedimentation, and ecosystem health, enabling early detection of potential issues like eutrophication or harmful algal blooms. Such monitoring also aids in the timely identification of infrastructure damage or disease outbreaks, which is essential for maintaining the economic viability of aquaculture operations. We can effectively detect these changes using multitemporal SAR images change detection methods, which provide near real-time, weather-independent data for informed decision-making.

# 6. Urban areas change detection

<div style="display: flex; justify-content: center; gap: 20px;">
  <figure style="margin: 0; text-align: center;">
    <img src="/images/urban_area_change_detection.png" alt="urban_area_change_detection" width="800" height="440">
  </figure>
</div>

Figure 6. Building area change detection using high-resolution multitemporal SAR images. Left: Temporal average, Right: change time visualization results.


Detecting changes in urban areas is essential for understanding and managing rapid urban growth, infrastructure modifications, and environmental impacts. Such change detection supports urban planning, helps update city data, and guides decision-making for sustainable development and disaster response. Multitemporal SAR image change detection methods are particularly valuable because they allow continuous monitoring regardless of weather or lighting conditions, providing timely, reliable insights into how cities evolve over time.

# 7. Flooding area visualization with RGB combination 

<img src="/images/flooding_area_monitoring.jpg" alt="flooding_area_monitoring" width="800" height="240">

Figure 7. Water area change visualization using RGB combination method based on 2 adjacent acquired SAR image (R: earlier acquisition, G: new acquisition, B: earlier acquisition). Magenta is the appearing water area, green is the area with increased backscattering values, and no additional color is added if there’s no change. Before combining the images, both SAR acquisitions are calibrated and coregistered to ensure they are aligned pixel‐to‐pixel. This step is crucial because even slight misalignments can create false change signals. No denoising method is needed if only visualize the change areas.
