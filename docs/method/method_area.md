---
title: "Methods for Survey Prev"
output:
  bookdown::html_book:
    number_sections: false
---

## <span style="color:royalblue">General idea</span>

The most common SAE method, introduced by Fay and Herriot
(1979)[@fay:herriot:79]. Under this approach the weighted estimates are linked together via a hierarchical model. The
rationale is that the similarity of prevalences across the study region may be leveraged to fine-tune the
estimates in each area. Since data from all areas is used for estimation in each area, this is an example of
the production of “indirect” estimates.

### Advantages 
- **Design-consistency**: Weighted estimates and uncertainty measures that feed into the hierarchical model account for the design, which avoids potential bias due to (say) stratified and PPS sample.
- **Reduced Uncertainty**: By modeling all the data in unison, uncertainty in each area is reduced (on average).
- **Reasonable Assumption**: The model that links the areas together is an additional assumption, when compared to the direct
estimates, but this is typically not a strong assumption.
- **Reduction in Mean-square Error**: The linking model will shrink high and low weighted prevalences toward the national weighted estimate, which is desirable when the data are sparse, but this does lead to (frequentist) bias. However, the rationale for the approach is that the gain in precision will offset the shrinkage bias. Specifically, there is theory that suggests that on average the mean-squared error ($\text{bias}^2$+variance) will be reduced for estimates from hierarchical models, when compared to direct estimates.

### Disadvantages
- **High Uncertainty with Sparse Data**:  The modeling is based on the weighted estimates and standard errors in each area, so when the data are sparse and estimates are not available or unreliable, the method cannot be used.
- **Inefficiency**: Since the data are data in each area are collapsed into a weighted estimate, it is not the most efficient
use of the data.
- **Harder Uncertainty Interpretation**: Interval estimates based on hierarchical models do not typically have the usual frequentist coverage, when each area is viewed in isolation. Across the map the coverage will be close to nominal (Burris and Hoff, 2020)[@burris:hoff:20], but explaining the uncertainty in each area is more tricky.
- **Computational Complexity**:  The computation is more intensive, as compared to direct estimates, but the method used in the
package is very efficient, and computation time not prohibitive.

## <span style="color:royalblue">Mathematical details</span>

Fay-Herriot models provides smoothed estimates at the areal level using direct estimate $\hat p^{W}_{i}$ as input. The direct estimates are modeled as a noisy observation of the true prevalence, with the variance of noise determined by the design-based variance. We consider the spatial Fay-Herriot model for the logit transformed direct estimates, which is defined as follows:

$$\text{logit}(\hat p^{W}_{i})|\lambda_{i} \sim\textrm{Normal}(\lambda_{i}, V_{i}^{HT}),$$

$$\lambda_{i}= \alpha + e_i+S_i.$$

Here $\text{expit}(\lambda_{i})$ is the latent true prevalence and $V_{i}^{HT}$ is the design-based variance, and $e_i$ and $S_i$ are unstructured and structured spatial random effects. Inference is carried out using Bayesian methods and so the model specific is completed by priors on $\alpha$, $e$ and $S$, and their hyperpriors. More details of the Bayesian model setup can be found in Wakefield, Okonek, and
Pedersen (2020)[@wakefield:okonek:pedersen:20]. Area level Fay-Herriot model are viewed as the most reliable model choice, since they acknowledge the design through the sue of a weighted estimate and its associated variance. See chapters 4 to 6 of Rao and Molina (2015)[@rao:molina:15].


As of now the package allows only an overall intercept $\alpha$, but future versions of the package will allow area level covariates to be included. The default prior for the intercept is $N(0, 1000)$. The structured and non-structured random effects are implemented used Besag-York-Mollié (BYM) via BYM2 parameterization, with default PC priors such that the marginal standard deviation has a prior such that $Prob(\sigma > 1) = 0.01$ and the proportion of variation explained by the spatial effect, $\phi$ has a prior such that $Prob(\phi \gt 0.5) = \frac{2}{3}$ (Riebler et al. 2016[@riebler:etal:16]; Simpson et al. 2017[@simpson:etal:17]).

The app implements spatial Fay-Herriot models at different administrative levels using `surveyPrev::fhModel()` and internally `SUMMER::smoothSurvey()`.

A Fay-Herriot model at fine spatial level (over Admin-2) can be fitted by treating areas without direct estimates as missing data, though <span style="color:orange">it is usually not recommended due to data sparsity</span>. In addition, numerical issue arise when design-based variance of direct estimate is close to zero and logit precision become too large. Our implementation fixes this issue by identifying regions with too small design variance (<1e-30), and deleting the clusters in these regions, before fitting the model. However, this step creates <span style="color:red">additional bias</span> in the results if the number of clusters deleted is large.
