# Ridge Plot

Ridge plots are a useful tool for visualizing the **full distribution of prevalence estimates** across different areas, especially when uncertainty is a significant factor. The peaks of each curve in a ridge plot indicate where the true value of the prevalence is most likely to be, offering an intuitive sense of the estimate's concentration. By comparing curves acorss regions, we can identify areas where estimates are notably higher or lower in an informal yet informative way. Overlapping curves suggest that the estimates are not significantly different when accounting for uncertainty, while distinct, non-overlapping curves indicate clear differences between regions. 

To enhance visual clarity, we avoid comparing too many regions at once, as this would result in a cluttered display. In the Shiny app, users can generate customized ridge plots by selecting from the following options:

- **All regions within an admin-1 level**, useful when the country has a manageable number of admin-1 regions.
- **All finer-scale regions within a selected upper admin region**, such as all admin-3 regions within a particular admin-2 region.
- **Regions with extreme values** at a selected admin level, where users can freely choose the number of regions (e.g., top 3, 4, etc.) to display, focusing on those with the highest and lowest estimates.

<div>
    <img src="../maps/RW_adm3_unit_ridge_extremes.png" style="width: 100%; height: auto">
</div>

The ridge plot above highlights the 5 regions with the most extreme prevalence estimates—both the lowest and highest—among over 100 admin-3 regions in Rwanda. Regions with the highest and lowest estimates clearly demonstrate significant differences, as their posterior distributions show minimal overlap. However, within the group of highest or lowest regions, the distributions are similar, indicating no significant differences among them. Notably, all regions with the lowest estimates are concentrated within the same admin-2 region, Rusizi.



