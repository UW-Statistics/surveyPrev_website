# Scatter Plot

A scatter plot is a powerful tool for comparing model estimates by plotting the results of two different models against each other. Each point on the scatter plot represents the value of the same statistic (such as the mean) in a specific region, with its position determined by the estimates from the two models. This visual approach enables you to quickly assess the level of agreement between models and evaluate their performance across different [statistical methods](../method/approach_overview.md).

In the Shiny app, users can choose which fitted models to display on each axis and select a **statistical measure** to compare, such as the mean, width of 95% confidence intervals, or coefficient of variation. The interactive plot includes a hover effect that displays the estimates for the selected statistical measure in each region, based on the two models chosen. Example comparisons can be found below.

### Comparing Point Estimates

<div>
    <iframe src="../maps/RW_adm2_scatter_mean.html" style="border: none; width: 100%; height: 500px;margin-bottom:-6em;margin-left:4em"></iframe>
</div>

The plot above compares the **mean estimates** of contraceptive usage among women aged 15-49 in Rwanda. Each point represents model estimates for an Admin-2 region, with direct estimates on the x-axis and area-level model estimates on the y-axis. Compared to direct estimates, the smoothing model estimates are slightly pulled towards the overall mean. This phenomenon is expected, as these models borrow information from neighboring regions to improve precision. However, when estimates are excessively drawn toward the mean (points align almost horizontally), particularly for other models at finer spatial scales, it indicates **over-smoothing**. This attenuation relative to direct estimates underscores the extent of smoothing, and results should be interpreted with greater caution in cases of over-smoothing.

### Comparing Uncertainty Measures

<div>
    <iframe src="../maps/RW_adm2_scatter_CI.html" style="border: none; width: 100%; height: 500px;margin-bottom:-6em;margin-left:4em;"></iframe>
</div>

The plot above compares the **width of 95% CIs** for contraceptive usage among women aged 15-49 in Rwanda. Each point represents the uncertainty measure for an Admin-2 region, with direct estimates on the x-axis and area-level model estimates on the y-axis. Compared to direct estimates, the smoothing model demonstrates reduced uncertainty, as indicated by narrower interval widths. This reduction is expected, as these models **borrow information** from neighboring regions to enhance precision, with the most significant decreases in uncertainty observed in regions that initially had sparse data.