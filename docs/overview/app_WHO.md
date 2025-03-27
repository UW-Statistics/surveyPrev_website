
This version of the app is tailored for use in WHO-hosted technical workshops and includes modifications to adhere to specific WHO regulations. Notably, it does not contain internally stored country boundary files; instead, users have to download the required shapefile directly from the WHO GIS Hub (see the implementation guide prepared by WHO for details). Additionally, the WHO version app does not include basemaps in visualizations.

There are three primary methods for utilizing the R Shiny application. The Docker deployment is the WHO recommended approach to accommodate internet instability.

1.  **Web-Based Tool**:

    - Location: Deployed on an online server.
    - Requirements: Internet access and a web browser.
    - Usage: Ideal for users who prefer quick access without local setup.

2.  **Local R Package Installation**:

    - Location: on user’s machine, launched by RStudio.
    - Requirements: R environment and dependent packages.
    - Usage: Suitable for users who wish to run the application directly
  within their local R environment. This method allows for enhanced
  customization.

3.  **Docker Deployment**:

    - Location: on user’s machine.
    - Requirements: Docker Desktop installation.
    - Usage: Perfect for users who do not have R installed but prefer to run
  the Shiny app locally. This method encapsulates the application within
  a Docker image, simplifying environment setup and ensuring
  compatibility.

Further details on the usage of this application via the above methods,
including step-by-step guide for installation, are available in the
subsequent sections.

## Web-based R Shiny app

The RShiny app is readily accessible via
<https://rsc.stat.washington.edu/saeforhealth/>. The only requirement is
a stable internet connection. This web-based deployment supports full
functionality and serves as the primary distribution channel.

## Installation of the R Shiny app as a R package

The installation and setup procedure for the WHO workshop version of the `sae4health` app is the same as for the [DHS-general version](../overview/app_general.md), except for the following additional step:

``` r
sae4health::run_app(version='DHS-WHO')
```



## Deploy the R Shiny app as a Docker image

The user need to first install the Docker desktop app from
<https://docs.docker.com/get-docker/>. Windows users may need to enable
the Windows Subsystem for Linux (WSL), which can be done by executing
the ‘wsl –install’ in the command line. Several methods are available
for deploying this RShiny app locally using Docker. Special thanks to
@Charlton Callender for providing these deployment techniques.

### Docker desktop app

1.  Open the Docker desktop app

2.  Download the image:

    - This is only required the first time you use the app or for
      downloading a new version/tag.
    - In the search bar, search for ‘yunhanwu/saeforhealth:v1.1.0’. (or the most recent version tag)
    - Hover cursor over relevant result and click ‘Pull’.

3.  Run a container with the downloaded image:

    - From sidebar, open ‘Images’ -\> ‘Local’. Should now have a row for
      ‘Name’=‘yunhanwu/saeforhealth’ and ‘Tag’=‘v1.1.0’.
    - Under actions click ‘Run’ (the play button).
    - Expand ‘optional settings’.
      - Under ‘Ports’: Fill ‘Host port’ with ‘3838’.
    - Click ‘Run’

4.  Open the RShiny app in your web browser by navigating to
    ‘<http://localhost:3838/>’.

5.  When done, close the webpage and:

    - From sidebar, open ‘Containers’.
    - Look for rows with ‘Image’=‘yunhanwu/saeforhealth’ & Status =
      ‘Running’.
    - Under ‘Actions’ click ‘Stop’

### Command line (with internet access)

1.  Open the command line.

2.  Download the image: `docker pull yunhanwu/saeforhealth:v1.1.0` (or the most recent tage)

3.  Run a container with the downloaded
    image:　`docker run --rm -p 3838:3838 yunhanwu/saeforhealth:v1.1.0`

4.  Open the RShiny app in your web browser by navigating to
    ‘<http://localhost:3838/>’.

5.  When done, close the webpage and:

    - From sidebar, open ‘Containers’.
    - Look for rows with ‘Image’=‘yunhanwu/saeforhealth’ & Status =
      ‘Running’.
    - Under ‘Actions’ click ‘Stop’

### Command line (with file copy of image)

1.  Open the command line.

2.  Obtain the docker image in tar format from another source. Load into
    docker with: `docker load --input file_path.tar`

3.  Run a container with the downloaded
    image:　`docker run --rm -p 3838:3838 yunhanwu/saeforhealth:v1.1.0`

4.  Open the RShiny app in your web browser by navigating to
    ‘<http://localhost:3838/>’.

5.  When done, close the webpage and:

    - From sidebar, open ‘Containers’.
    - Look for rows with ‘Image’=‘yunhanwu/saeforhealth’ & Status =
      ‘Running’.
    - Under ‘Actions’ click ‘Stop’