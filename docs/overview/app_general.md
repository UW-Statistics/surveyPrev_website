
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

The RShiny app is readily accessible via
<https://rsc.stat.washington.edu/surveyPrevRShiny/>. The only
requirement is a stable internet connection. This web-based deployment
supports full functionality and serves as the primary distribution
channel.

This version uniquely includes preloaded shapefiles. If using other
versions of the app, users will need to download or upload shapefiles
manually; however, this process has been streamlined into simple steps
for ease of use.

## Installation of the R Shiny app as a R package

Some non-CRAN dependencies can be installed using the following command.
We strongly recommend installing the most recent version of SUMMER and
surveyPrev package from Github.

``` r
# install.packages("devtools")
devtools::install_github("rspatial/geodata")
devtools::install_github("richardli/SUMMER")
devtools::install_github("richardli/surveyPrev")
devtools::install_github("statnmap/HatchedPolygons")
devtools::install_github("qianyu313/surveyPrevGithub")

install.packages("INLA",repos=c(getOption("repos"),
                        INLA="https://inla.r-inla-download.org/R/testing"),dep=TRUE)
```

You can then install the development version of saeforhealth with:

``` r
devtools::install_github("wu-thomas/SurveyPrevRShiny")
```

Our tool depends specifically on 2.12.0 version of the labelled package,
so we make sure the correct version is used.

``` r
remotes::install_version("labelled", "2.12.0")
```

You can launch the RShiny app with the following command, and we
recommend opening a new browser tab from within the launched RShiny app
for better accessing web links.

``` r
library(SurveyPrevRShiny)
SurveyPrevRShiny::run_app()
```