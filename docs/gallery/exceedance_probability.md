# Exceedance Probability Maps

The **exceedance probability** is a highly informative measure that quantifies the likelihood that the prevalence  \( p \) in an area exceeds a specified threshold  \( c \) [^1]. This measure serves as a valuable inferential tool, similar to hypothesis testing, by assessing *how likely it is that the prevalence surpasses a given value*. This is particularly useful for decision-making; for example, if the probability that the prevalence of a disease in a region exceeds a certain standard is high (e.g., 0.95), policymakers can confidently conclude that the prevalence is likely above the threshold, prompting more urgent action.

<div>
    <iframe src="../maps/RW_adm3_unit_exceed_prob.html" style="border: none; width: 100%; height: 500px;"></iframe>
</div>

The map above shows the probability that contraceptive usage among women aged 15-49 exceeds the national average across regions in Rwanda, based on a unit-level model. In the Shiny app, the **default threshold  \( c \) is set to the national average**, but this can be easily adjusted using the slider to any threshold of interest. Darker colors indicate a higher probability that the prevalence is above the national average. In this example, regions in the lower left, with an exceedance probability of less than 5%, may warrant special attention as they are significantly below the national average.



[^1]: To be specific, given the posterior \( f(p \mid \text{data}) \), the probability that prevalence \( p \) exceeds a threshold \( c \) is:\( P(p > c \mid \text{data}) = \int_{c}^{1} f(p \mid \text{data}) \, dp \). In area-level and unit-level models, we calculate this integral using posterior draws. For direct estimation methods, we obtain samples from normal distributions parameterized by the point estimates and standard errors of the weighted estimates.



