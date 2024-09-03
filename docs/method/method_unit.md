---
title: "Methods for Survey Prev"
output:
  bookdown::html_book:
    number_sections: false
---

## <span style="color:royalblue">General idea</span>

This SAE method was introduced by (Battese et al., 1988)[@battese:etal:88] and is the closest to a conventional model-based approach, since a sampling model is used at the cluster-level, specifically an overdispersed binomial model. As with the area-level model, the area-specific prevalences across areas are linked via a hierarchical model. Again, the rationale is that the similarity of prevalences across the study region may be leveraged to fine-tune the estimates in each area. Since data from all areas is used for estimation in each area, this is another example of the production of “indirect” estimates.

### Advantages
- **Sparse Data Handling**: If the data are sparse, this is the only method that can be used, since the cluster-level overdispersed
binomial model can deal with situations in which the responses are either all 0s or all 1s (this sparse
data case leads to problems for methods based on weighted estimates since the estimates themselves
are 0 or 1 and the methods collapse).
- **Efficiency**: If the sampling model is a reasonable approximation to the true underlying data generating mechanism,
the approach is an efficient use of the data.
- **Uncertainty Reduction**: By modeling all the data in unison, uncertainty in each area is reduced (on average).
- **Reasonable Assumption**: The model that links the areas together is an additional assumption, when compared to the direct
estimates, but this is typically not a strong assumption.
- **Mean-squared Error Reduction**: The linking model will shrink high and low weighted prevalences toward the national estimate, which is desirable when the data are sparse, but this does lead to (frequentist) bias. But the rationale for the approach is that the gain in precision will offset the shrinkage bias. Specifically, there is theory that suggests that on average the mean-squared error (bias2+variance) will be reduced for estimates from hierarchical models, when compared to direct estimates.

### Disadvantages
- **Sampling Model**: The assumption of a sampling model for the cluster-level responses means this approach is fundamentally
different from the direct and area-based methods which use weighted estimates.
- **Extra Design Adjustment Needed**: Since the weights are not used, one must adjust for the design within the model specification by
modeling the association between prevalence and urban/rural and including a cluster effect in the sampling model.
- **Over-Shrinkage**: When the data are sparse, the estimates may be shrunk too much since the data are not sufficiently
informative to discriminate from the “flat” map case.

### <span style="color:royalblue">Mathematical details</span>
