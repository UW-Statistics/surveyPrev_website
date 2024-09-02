# Uncertainty Maps

It is imperative that measures of uncertainty accompany a point estimate in each area. Relying solely on point estimates can be misleading as they may suggest a definitive ranking that could disappear when the accompanying uncertainty is factored in. This consideration is especially pertinent in Small Area Estimation (SAE), where information is typically sparse, particularly in the context of Admin-2 areas. It is essential to account for the uncertainty of indicator estimates when interpreting results and making inference.

## Width of the 95% Credible Interval (CI)

Credible Intervals[^1] are Bayesian analogs of confidence intervals, which in plain language, means the data user can be highly confident that the true value of that estimated indicator falls between the high and low values presented. Specifically, a 95% credible interval suggests that there is a 95% probability that the true value lies within this range, given the evidence provided by the observed data. Wider credible intervals indicate we are less certain of the estimate, while narrower credible intervals indicate we are more certain of the estimate.


<div>
    <iframe src="../maps/RW_adm3_unit_CI_width.html" style="border: none; width: 100%; height: 500px;"></iframe>
</div>

The map above displays the widths of 95% credible intervals across regions in Rwanda, for contraceptive usage among women aged 15-49. The results are produced by a unit-level model. Darker colors represent wider credible intervals, indicating higher uncertainty in the estimates.

[^1]: Area-level and unit-level models are constructed under Bayesian framework for which we use credible intervals. For the direct (weighted) estimates, we use frequentist confidence interval. See the [methodology section](../method/approach_overview.md) for more details.
## Coefficient of Variation (CV)

When a prevalence, which is constrained to lie between 0 and 1, is considered, the coefficient of variation (CV) is particularly useful. It quantifies the extent of variability in relation to the size of the point estimate. The CV is often expressed as a percentage and, for the weighted estimator, is defined as:

\[
CV = 100 \times \frac{\text{Standard Error}}{\text{Point Estimate}}
\]

For example, if 

1. The point estimate is \( \hat{p} = 0.1 \) and the standard error is 0.05, then we have a CV of 50%, which would be viewed as indicating large uncertainty. 
2. By contrast, if the point estimate is \( \hat{p} = 0.5 \) and the standard error is again 0.05, then we have a CV of 10%, which may be viewed as reasonable. 

When Bayesian methods are used for inference, the standard error is replaced by the posterior standard deviation.

<div>
    <iframe src="../maps/RW_adm3_unit_CV.html" style="border: none; width: 100%; height: 500px;"></iframe>
</div>

The map above displays the coefficient of variation across regions in Rwanda, for contraceptive usage among women aged 15-49. The results are produced by a unit-level model. Darker colors represent higher coefficient of variation, indicating higher level of variability with repect to the prevelence level.
