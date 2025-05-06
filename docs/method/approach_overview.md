
Here is the written documentation for our method. Additionally, explore our engaging [**video lecture**](../overview/youtube_method_lecture.md) presented by Professor <a href="https://faculty.washington.edu/jonno/" target="_blank">Jon Wakefield</a> from University of Washington. The slides are available [**here**](../overview/sae_slides.md). To cite SAE4Health in publications, please use 
> Wu, Y., Dong, Q., Xu, J., Li, Z. R., & Wakefield, J. (2025). *sae4health: An R Shiny Application for Small Area Estimation in Low- and Middle-Income Countries.* arXiv:2505.01467. [https://doi.org/10.48550/arXiv.2505.01467](https://doi.org/10.48550/arXiv.2505.01467).

## Small Area Estimation (SAE)

<em>**Small area estimation (SAE)**</em> refers to the process of producing estimates of quantities of interest—such as <span style="color:#1a7f42;"><strong>prevalence rates</strong></span>—for specific geographic areas, even when data are sparse or unavailable. The <a href="https://github.com/richardli/surveyPrev" target="_blank">`surveyPrev`</a> R package and the `sae4health` R Shiny app are designed to generate such estimates using <span style="color:#1a7f42;"><strong>household survey data</strong></span>.

These data are typically collected through <span style="color:#0056b3;"><strong>complex sampling designs</strong></span> (e.g., stratified, two-stage cluster sampling), which must be accounted for during modeling. SAE4Health integrates methods from <span style="color:#1a7f42;"><strong>survey sampling</strong></span> and <span style="color:#1a7f42;"><strong>SAE</strong></span> to produce reliable subnational estimates and quantify associated uncertainty.

Mapped outputs offer intuitive visualizations of <span style="color:#0056b3;"><strong>geographic variation</strong></span>. When paired with uncertainty intervals, these estimates help identify areas most in need of targeted intervention.

---

### Administrative Levels of Analysis

We follow a common convention for defining administrative levels:

- <span style="color:#c65f1e;">Admin-0</span>: National  
- <span style="color:#c65f1e;">Admin-1</span>: First subnational level (e.g., regions or provinces)  
- <span style="color:#c65f1e;">Admin-2</span>: Second subnational level (e.g., districts or municipalities)

For example, in Nigeria:

- <span style="color:#c65f1e;">Admin-0</span> is the national level,
- <span style="color:#c65f1e;">Admin-1</span> corresponds to its 36 states plus Abuja
- and <span style="color:#c65f1e;">Admin-2</span> includes the 774 Local Government Areas (LGAs) nested within states.

Administrative structures differ across countries, but they generally follow this nested hierarchy.

---

### Survey Design Considerations

Most **Demographic and Health Surveys (DHS)** and **Multiple Indicator Cluster Surveys (MICS)** follow a <span style="color:#0056b3;"><strong>stratified two-stage cluster sampling</strong></span> design:

1. <strong>Stratification</strong> is typically based on a cross of <span style="color:#0056b3;">urban/rural status</span> and <span style="color:#0056b3;">Admin-1 regions</span>.
2. In the <em>first stage</em>, clusters (enumeration areas) are sampled using <em>probability proportional to size (PPS)</em>.
3. In the <em>second stage</em>, a fixed number of households (e.g., 25) are randomly selected within each cluster.

Surveys are typically powered to produce estimates at the <span style="color:#c65f1e;">Admin-1</span> level. SAE methods make it possible to derive stable estimates at the finer <span style="color:#c65f1e;">Admin-2</span> level.

---

### Modeling Approaches

The <code>surveyPrev</code> package and Shiny app provide three [SAE modeling options](../method/approach_overview.md) in line with the standard classification from Rao and Molina (2015)[@rao:molina:15].

<!-- Small area estimation (SAE) describes the endeavor of producing estimates of quantities of interest, in our case prevalences, for a set of areas, with the possibility of sparse response data in at least some areas. The `surveyPrev` package and accompanying shinyapp is designed to produce small area prevalence estimates using household survey data. The household data are collected with a complex design (stratified, cluster sampling) and this must be recognized in the modeling. To this end, methods from survey sampling and SAE are used for modeling.

Once small area estimates are produced, they may be mapped to see a visual picture of the pattern of prevalence over the study region. With a set of estimates, along with their uncertainty, one can gain valuable insight into which areas are struggling with particular indicators, which may be a motivation for introducing interventions.

In the following, Admin-0 refers to the national level, Admin-1 to one level beneath that, and Admin-2 to one beneath that, with each set of areas being nested in the level above. As an example, Nigeria has 774 local government areas (Admin-2 areas) which are nested within 36 states (Admin-1 areas). In general, the numbers of Admin-1 and Admin-2 areas shows large variation across countries.

In the context of household surveys, the usual sampling is stratified two-stage cluster sampling. We note that surveys in some countries deviate from the following description, but most Demographic Health Surveys (DHS) and Multiple Indicator Cluster Surveys (MICS) surveys follow this design. The strata are based on a cross-classification of urban/rural with Admin-1 areas. In the first stage, clusters are samples within strata, using probability proportional to size (PPS), with the sizes being the numbers of households. At the second stage, a fixed number of households (for example, 25) is probabilistically sampled from those available. The surveys often take sufficient clusters for reasonably accurate inference for key indicators at the Admin-1 level.

Three distinct approaches are provided in the package and shinyapp, in line with a standard SAE categorization (Rao and Molina, 2015)[@rao:molina:15]. -->