## Purpose of the Tool
The R package and Shiny app were developed to facilitate hands-on analysis of health and demographic indicators in low- and middle-income countries (LMICs) at the subnational level. The primary aim is to support programming and interventions, as well as monitor progress toward targets such as the Sustainable Development Goals (SDGs). By providing tools for detailed analysis, the package and app help to generate subnational estimates of various indicators, enabling stakeholders to make informed decisions at different geographic levels.

## Target Audience
This tool is designed for a broad range of users, including:

- **Policymakers**: Who need to assess the impact of health and demographic interventions at local levels.
- **Researchers**: Engaged in studying health trends and demographic shifts within countries.
- **Public Health Professionals**: Working to implement programs and monitor outcomes at subnational levels.

## General Aims of the Project
The project is centered around several key objectives:

- **Programming and Interventions**: To provide actionable data that can guide health and demographic interventions at the subnational level.
- **Monitoring Progress**: To track progress toward achieving the SDGs and other health-related targets, particularly at smaller administrative levels.
- **Handling Various Indicators**: To offer tools for analyzing a wide range of prevalence indicators (e.g., neonatal mortality rate, vaccination coverage, stunting).
- **Addressing Within-Country Variation**: To account for geographical variation in health and demographic indicators across different areas within a country.

## Geographic Levels of Analysis
The tool supports analysis across different levels of geographic hierarchy:

- **Admin0 (National Level)**: Provides estimates for the entire country.
- **Admin1 (First Subnational Level)**: Offers estimates for large regions or states within the country.
- **Admin2 (Second Subnational Level) and Finer**: Provides estimates for smaller areas, such as districts or municipalities.

## Small Area Estimation (SAE)
The [core methodology](../method/approach_overview.md) implemented in the tool is Small Area Estimation (SAE). SAE is essential for generating reliable estimates in areas where data may be sparse. It involves estimating a variable of interest within specific geographic areas, with a focus on accuracy despite potentially limited data availability.


