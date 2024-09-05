# Prevalence Maps

Prevalence maps are essential tools for visualizing the variation in health and demographic indicators across geographic regions.  These maps provide **point estimates** that reflect the spatial variation in health outcomes, such as the prevalence of modern contraceptive use or vaccination rates. 

Unless a complete enumeration of the relevant population is carried out, we will not know the prevalence with certainty, and associated with each area is a **range** of plausible values, hence it is essential to always examine the **uncertainty measures**, as well as the point estimate summary.

Our interactive map enhances user engagement with a hover effect that displays region-specific information, including region names and **uncertainty measures**, which, as just noted, are essential for accurately interpreting the results alongside point estimates (check out [uncertianty maps](uncertainty_CI_CV.md) and [ridge plots](ridge_plot.md)). The hover effect is consistent across all maps, yet each single map specifically displays only one statistical measure. To compare different methods or measures across maps, please refer to the [comparison maps](map_comparisons.md).

## Unit-level Model Results

<div>
    <iframe src="../maps/RW_adm3_unit_mean.html" style="border: none; width: 100%; height: 500px;"></iframe>
</div>

The above prevalence map illustrates contraceptive usage among women aged 15-49 in Rwanda at the Admin-3 level, using a [unit-level model](../method/method_unit.md) based on the 2019 Rwanda DHS data. This model employs <span style="color: blue">spatial smoothing </span>, which enhances estimates in data-sparse areas by <span style="color: blue"> borrowing information from neighboring regions</span>, thereby ensuring a smoother visual representation across the map. The specific map indicates higher contraceptive usage in the northeastern regions compared to the southwestern parts of the country. Such spatial patterns are commonly observed in these maps. Users are encouraged to further interpret these results, using country-specific insights to delve into the underlying reasons, and/or tailor interventions based on local needs and conditions. 

## Direct Estimates Results

In general, direct estimation methods yield reliable results at broader spatial scales such as national or Admin-1 levels. However, at more granular levels like Admin-3, these methods often fail to provide accurate estimates, a limitation we will explore through the following map for the same indicator (contraceptive usage among women aged 15-49 in Rwanda). 

<div>
    <iframe src="../maps/RW_adm3_direct_mean.html" style="border: none; width: 100%; height: 500px;"></iframe>
</div>

Notably, about a third of the regions had no data at all, represented by grey coloring, leading to uncalculated estimates. This occurs in direct estimates methods because estimation here <span style="color: blue">depend solely on region-specific data</span>, unlike in the unit-level model which borrows information from neighboring regions. In areas with available data, direct estimation still presents challenges. Specifically, when data come from a limited number of clusters, prevalence estimates may reach extreme values of zero or one, and standard methods for calculating standard errors become inapplicable due to small sample sizes. This inability to validly measure uncertainty is indicated by the grey hatching in these regions. Furthermore, for regions with valid estimates, the associated uncertainties are often very high, making points estimate less reliable. 

This considerable uncertainty and the potential unreliability of these estimates at fine spatial scale necessitate caution in interpretation. Both the grey filled colors and grey hatching serve as visual cues to highlight areas where <span style="color: blue">data scarcity undermines the robustness of estimates</span> from direct estimates method, underscoring the need for the unit-level model approach shown in the earlier map.


<!-- <iframe src="https://www.youtube.com/watch?v=iV2gBOHhggs" allowfullscreen></iframe> -->
