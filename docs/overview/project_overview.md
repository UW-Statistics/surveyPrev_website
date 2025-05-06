## Purpose of SAE4Health

Achieving health-related Sustainable Development Goals (SDGs) requires reliable data not only at the national level, but also at finer geographic scales. Yet producing accurate estimates at the subnational level in low- and middle-income countries (LMICs) often demands advanced statistical modeling and complex software implementation — resources that are typically out of reach for the local policymakers and practitioners who know the health systems best.

**SAE4Health** is a capacity-building initiative developed by researchers at the University of Washington to bridge this gap. It brings together <span style="color:#1a7f42;">**training**</span>, <span style="color:#1a7f42;">**statistical methodology**</span>, and <span style="color:#1a7f42;">**accessible tools**</span> to make small area estimation (SAE) usable by all audiences. At the center is the user-friendly [**`sae4health`**](../overview/app_general.md) R Shiny application, which enables hands-on modeling and visualization of subnational health estimates — without requiring any programming expertise.

The [**`sae4health`**](../overview/app_general.md) app draws on statistical methods implemented in the <a href="https://github.com/richardli/surveyPrev" target="_blank">**`surveyPrev`**</a>  R package and supports both **DHS-based** ([**DHS version**](../overview/app_general.md)) and **MICS-based** ([**MICS version**](../overview/app_MICS.md)) workflows. Users can use household survey data and generate SAE-based estimates across different administrative levels through an interactive interface.

SAE4Health is designed not only to produce actionable subnational estimates, but also to build local capacity in statistical reasoning, enabling users to better understand, interpret, and apply model-based results in real-world policy and planning contexts.


<!-- Our <a href="https://github.com/richardli/surveyPrev" target="_blank">**surveyPrev R package**</a> and Shiny apps (<a href="https://rsc.stat.washington.edu/surveyPrevRShiny" target="_blank">**DHS version**</a> and <a href="https://rsc.stat.washington.edu/surveyPrevRShinyMICS" target="_blank">**MICS version**</a>), were developed to empower hands-on analysis of health and demographic indicators in low- and middle-income countries (LMICs) at the subnational level. The primary goal is to support programming, interventions, and monitoring of progress toward the Sustainable Development Goals (SDGs). Designed to be user-friendly and accessible without prior statistical or programming knowledge, the tools not only facilitate detailed analysis but also embed statistical thinking, enabling users to conduct statistical inference through comprehensive tutorials and creative visualization tools. -->


## Target Audience

SAE4Health is designed for institutions and individuals involved in subnational health data analysis and decision-making, including but not limited to:

- **Ministries of Health** using data for planning and monitoring.
- **National Statistics Offices** responsible for producing official health estimates.
- **Subnational policymakers** at the district or provincial level.
- **Researchers and universities** applying SAE methods in training and public health research.
- **Health program implementers** who use local estimates to guide interventions.

## Core Objectives

SAE4Health supports country-led efforts to strengthen subnational health data use through:

- <span style="color:#1a7f42;">**Capacity building**</span>: Train national teams to apply SAE methods and interpret results for planning and policy.

- <span style="color:#1a7f42;">**Data-informed planning**</span>: Support the development of strategies guided by model-based estimates across diverse health indicators.

- <span style="color:#1a7f42;">**Knowledge exchange**</span>: Facilitate cross-country learning and build a network of technical experts for sustained use.

## Methodological Details

The statistical approach behind SAE4Health is centered on advanced SAE methodology, as described in the [**methods**](../method/approach_overview.md) section. There you’ll find an overview of the modeling framework, estimation strategy, and how uncertainty is quantified across geographic levels. To cite SAE4Health in publications, please use 
> Wu, Y., Dong, Q., Xu, J., Li, Z. R., & Wakefield, J. (2025). *sae4health: An R Shiny Application for Small Area Estimation in Low- and Middle-Income Countries.* arXiv:2505.01467. [https://doi.org/10.48550/arXiv.2505.01467](https://doi.org/10.48550/arXiv.2505.01467).




<!-- 
## Geographic Levels of Analysis
The tool supports analysis across different levels of geographic hierarchy:

- **Admin-0 (National Level)**: Provides estimates for the entire country.
- **Admin-1 (First Subnational Level)**: Offers estimates for large regions or states within the country.
- **Admin-2 (Second Subnational Level) and Finer**: Provides estimates for smaller areas, such as districts or municipalities.

## Small Area Estimation (SAE)
The [core methodology](../method/approach_overview.md) implemented in the tool is Small Area Estimation (SAE). SAE is essential for generating reliable estimates in areas where data may be sparse. It involves estimating a variable of interest within specific geographic areas, with a focus on accuracy despite potentially limited data availability. -->


