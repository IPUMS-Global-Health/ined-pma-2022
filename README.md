# July 2022 INED Data Analysis Workshop 
### Linking health survey data with different climate datasets in R 
### July 6, 2022 14:00 - 16:00 (GMT+2)

Welcome! If you're looking for free registration for the in-person coding workshop, please [click here](https://www.ined.fr/en/news/scientific-meetings/seminaries-colloque-ined/population-environment-health-connecting-pixels/).

All data and software (R) featured in this workshop are available free of charge.

# 	:bangbang: Please Complete Setup Before the Workshop Begins

Setup: 

  1. [Download and Install RStudio](https://www.rstudio.com/products/rstudio/download/#download) (and [R](https://cran.r-project.org/)) if you do have not already done so.
  2. Install the spatial analysis tools [GEOS](https://libgeos.org/), [GDAL](http://www.gdal.org/), and [PRØJ](http://proj.org/) **using the appropriate instructions for your operating system**.
      - **Windows:** [Install RTools](https://cran.r-project.org/bin/windows/Rtools/). All three spatial analysis tools will be included.
      - **MacOS** Follow [these instructions](https://r-spatial.github.io/sf/index.html#macos) to install [GDAL](http://www.gdal.org/) using [Homebrew](https://brew.sh/), and then continue the instructions for installing `sf` and `rgdal` in R ([GEOS](https://libgeos.org/) and [PRØJ](http://proj.org/) will be installed automatically).
      - **Linux** Follow the appropriate instructions for your Linux distribution [shown here](https://r-spatial.github.io/sf/index.html#linux).
  3. [Register to use IPUMS PMA data](https://pma.ipums.org/pma/register.shtml).
      - :bar_chart:	you will need to be registered in order to **download data** during the workshop.
  4. Clone this repository, or simply [click here to download](https://github.com/matt-gunther/ined-pma-2022/archive/refs/heads/main.zip).
      - :open_file_folder: **Windows** users may need to download decompression software (e.g. [7-Zip](https://www.7-zip.org/)).
  5. Once downloaded, open the file `ined-pma-2022.Rproj`.
      - :rocket: this will open RStudio in a new project environment.
  6. Copy the following code into the `Console` in RStudio, then press `Enter`.
      - :hourglass: it may take several minutes to install the packages needed for this workshop!
      - Update any packages if prompted.
      - Reply "No" to `Do you want to install from sources the package which needs compilation?`.
      - **Recommended:** Restart R at least once before the workshop begins.
  
 ```
# Install any necessary packages if not already installed 

for(
  pkg in c(
    "tidyverse", "ipumsr", "sf", "terra", "ggspatial", "gtools",
    "srvyr", "survey", "lme4", "broom.mixed", "broom", "remotes"
  )
){if(!require(pkg, quietly = TRUE, character.only = TRUE)){install.packages(pkg)}}

# Install a development version of `ggspatial` that plots raster data from `terra`
# See https://github.com/paleolimbot/ggspatial/

if(packageVersion("ggspatial") != '1.1.5.9000'){
  remotes::install_local("cellar/ggspatial_1.1.5.9000.tar.gz")
}
 ```
  

# Slides and Source Code

[Click here for slides](https://matt-gunther.github.io/ined-pma-2022/slides.html) shown in the workshop (built with [Quarto and Revealjs](https://quarto.org/docs/presentations/revealjs/))

Source code is included in the file `analysis.Rmd`
