---
title: "Methods for Survey Prev"
output:
  bookdown::html_book:
    number_sections: false
---

## <span style="color:royalblue">General idea</span>

The starting point for analysis, with the prevalence being estimated as a weighted average of the cluster means. Inference follows from assuming that a normal distribution describes the variation in the estimator. Inference is **design-based**, meaning estimators are judged with respect to their frequentist properties over hypothetical repeats of the survey with a fixed population. The term **"direct"** refers to estimates in each area being based solely on data from that area.

### Advantages
- **Design-Consistency**: Estimates and uncertainty measures account for the design via weighting, avoiding bias due to informative sampling (e.g., oversampling of urban clusters). This leads to estimators that are approximately unbiased, which is highly desirable.
- **Accuracy in Large Samples**: When there are a large number of clusters in an area, confidence intervals constructed from the normality assumption are accurate for each area.
- **Minimal Assumptions**: No explicit model is required for the data, making this approach straightforward and intuitive to describe.
- **Applicability**: Often provides reasonable inference for Admin-1 areas, unless the outcome is very rare.

### Disadvantages
- **High Uncertainty with Sparse Data**: When data are sparse in an area, the estimator's uncertainty may be so high that the estimate is not useful. With few clusters, the point estimate of prevalence may be zero or one, making standard error calculations unreliable.
- **Inefficiency**: Collapsing data into a weighted estimate is not the most efficient use of the data.
- **Lack of Data Integration**: The large uncertainty associated with weighted estimates arises because estimates in each area rely solely on data from that area. This contrasts with area-level and unit-level approaches that **"borrow strength"** from data across all areas.
- **Sample Size Dependence**: The normality assumption relies on large sample sizes, but even when a point estimate and standard error are produced, sparse data can lead to inaccurate uncertainty intervals.

## <span style="color:royalblue">Mathematical details</span>

For \( y_j \) be the binary outcome of interest for the \( j^{\text{th}} \) individual in the survey and \( w_j \) be the design weight associated with this individual. For a given area denoted as \( i \), we have the weighted estimator: \( \hat{p}^{W}_{i} = \frac{\sum_{j \in S_i} y_j \cdot w_j}{\sum_{j \in S_i} w_j} \), where \( S_i \) is the set of individual index within the \( i \)-th region.

Direct estimates at different Admin levels are calculated using `surveyPrev::directEST()` in the **surveyPrev** package and `SUMMER::smoothSurvey()` function in the **SUMMER** package internally (Li et al. 2020)[@li2020space].

The confidence intervals are computed on the logit scale, i.e., if we use \( D_i \) to denote the design-based variance of \( \hat p^{W}_i \), then the asymptotic design-based variance of \( \text{logit}(\hat p^{W}_i) \) is

$$
V_i = \frac{D_i}{(\hat{p}^{W}_i)^2 \times (1 - \hat{p}^{W}_i)^2}
$$

and we compute the confidence interval on the probability scale by exponentiation of the confidence interval at logit scale.

Currently the our implementation defaults to a two-stage stratified cluster sampling design, with the sampling clusters (enumeration areas) being stratified by Admin-1 (certain countries Admin-2) areas and urban/rural strata, which is the most common sampling design in the DHS.
