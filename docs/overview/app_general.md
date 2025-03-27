
There are two primary venues to utilize this R Shiny application:

1.  **Web-Based Tool**:
    - Location: Deployed on an online server.
    - Requirements: Internet access and a web browser.
    - Usage: Ideal for users who prefer quick access without local setup.

2.  **Local R Package Installation**:
    - Location: on user’s machine, launched by RStudio.
    - Requirements: R environment and dependent packages.
    - Usage: Suitable for users who wish to run the application directly within their local R environment. This method allows for enhanced customization.

## Web-based R Shiny app

The R Shiny app is readily accessible via
<https://rsc.stat.washington.edu/surveyPrevRShiny/>. The only
requirement is a stable internet connection. This web-based deployment
supports full functionality and serves as the primary distribution
channel.

One advantage of the online version is that it includes preloaded
shapefiles, reducing the need for manual uploads. While all versions
require users to upload their own DHS survey datasets for analysis,
currently the online version internally hosts the 2018 Nigeria DHS, 2022
Kenya DHS, and 2023 Senegal DHS (**without the need for data upload!**),
with more datasets planned for future inclusion.

## Installation of the R Shiny app as a R package

The procedure for installing and running `sae4health` on your local machine is described below. You can also find the most up-to-date documentation on our <a href="https://github.com/wu-thomas/sae4health" target="_blank">GitHub repository</a>. 

Some non-CRAN dependencies can be installed using the following command.
We strongly recommend installing the most recent version of SUMMER and
surveyPrev package from Github.

``` r
# install.packages("devtools")
devtools::install_github("richardli/SUMMER")
devtools::install_github("richardli/surveyPrev")

install.packages("INLA",repos=c(getOption("repos"),
                INLA="https://inla.r-inla-download.org/R/testing"),dep=TRUE)
```

<!-- To install additional CRAN dependencies, run the following command:   -->
<!-- (Some dependencies are not listed in the CRAN `Imports` to meet submission requirements, so they need to be installed manually.) -->
<!-- devtools::install_github("rspatial/geodata") # for downloading GAM shapefile -->

`sae4health` will be published on CRAN soon. You can install the development version of `sae4health` with:

``` r
devtools::install_github("wu-thomas/sae4health")
```

<!-- Our tool depends specifically on 2.12.0 version of the labelled package, so we make sure the correct version is used.  -->
<!-- ``` {r, eval=F, echo=T} -->
<!-- remotes::install_version("labelled", "2.12.0") -->
<!-- ``` -->

Processing the analysis dataset for indicators, using specific coding
schemes and handling labels, requires the following libraries to be
**preloaded** before running the app:

``` r
library(labelled)
library(naniar)
library(sjlabelled)
library(dplyr)
library(data.table)
library(haven)
```

You can launch the R Shiny app with the following command, and we
recommend opening a new browser tab from within the launched R Shiny app
for better accessing web links.

``` r
library(sae4health)
sae4health::run_app()
```

If the colors in the interactive Leaflet maps appear inverted relative
to the legend (e.g., regions with high values in the legend are shown in
low-value colors), you can run the app with the following option. This
issue arises due to differences in R and Leaflet package versions and is
beyond our control.

``` r
sae4health::run_app(legend_color_reverse=T)
```