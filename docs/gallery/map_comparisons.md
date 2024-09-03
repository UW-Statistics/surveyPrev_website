# Comparison Maps

The Shiny app allows users to generate maps that facilitate side-by-side comparisons. 

## Different Statistical Measures from a Single Model

Users can plot different statistical measures from a single model, allowing for an easy comparison between point estimates and their associated uncertainties. The available statistical measures include the mean, width of 95% CIs, coefficient of variation, and exceedance probability. For instance, the maps below illustrate these various statistical measures for contraceptive usage among women aged 15-49 in Rwanda, based on the unit-level model at the Admin-3 level.

<div>
    <iframe src="../maps/RW_compare_maps_mean.html" style="border: none; width: 100%; height: 830px;"></iframe>
</div>

## Same Statistical Measures across Different Models

Alternatively, users can plot the same statistical measure across different models, providing a way to assess consistency and compare model performance. For example, the maps below compare point estimates of contraceptive usage among women aged 15-49 in Rwanda across different models. As the spatial resolution becomes finer, greater spatial disparities become apparent. The effect of smoothing is also noticeable when comparing Admin-2 estimates from the direct estimation model with those from the area-level model.

<div>
    <iframe src="../maps/RW_compare_maps_adm3_unit.html" style="border: none; width: 100%; height: 830px;"></iframe>
</div>



