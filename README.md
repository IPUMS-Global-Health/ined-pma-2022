# July 2022 INED Data Analysis Workshop 
### Linking health survey data with different climate datasets in R 
### July 6, 2022 14:00 - 16:00 (GMT+2)

Welcome! This repository contains presentation slides, data, and analysis code from the coding workshop hosted on July 6, 2022. Setup instructions are shown below. If you have any questions, please contact [Matt Gunther](https://github.com/matt-gunther) directly.

All data and software (R) featured in this workshop are available free of charge.

# 	:bangbang: Please Complete Setup Before the Workshop Begins

Setup: 

  1. [Download and Install RStudio](https://www.rstudio.com/products/rstudio/download/#download) (and [R](https://cran.r-project.org/)) if you do have not already done so.
  2. Install the spatial analysis tools [GEOS](https://libgeos.org/), [GDAL](http://www.gdal.org/), and [PRØJ](http://proj.org/) **using the appropriate instructions for your operating system**.
      - **Windows:** [Install RTools](https://cran.r-project.org/bin/windows/Rtools/). All three spatial analysis tools will be included.
      - **MacOS** Follow [these instructions](https://r-spatial.github.io/sf/index.html#macos) to install [GDAL](http://www.gdal.org/) using [Homebrew](https://brew.sh/), and then continue the instructions for installing `sf` and `rgdal` in R ([GEOS](https://libgeos.org/) and [PRØJ](http://proj.org/) will be installed automatically).
      - **Linux** Follow the appropriate instructions for your Linux distribution [shown here](https://r-spatial.github.io/sf/index.html#linux).
  4. Clone this repository, or simply [click here to download](https://github.com/matt-gunther/ined-pma-2022/archive/refs/heads/main.zip).
      - :open_file_folder: **Windows** users may need to download decompression software (e.g. [7-Zip](https://www.7-zip.org/)).
  5. Create a data extract from [IPUMS PMA](https://pma.ipums.org/pma-action/variables/group?unit_of_analysis=person) with the following elements (visit the [IPUMS PMA Youtube Channel](https://www.youtube.com/playlist?list=PLHMF4C5RDaejhm4Hdm3fulvaoKkhTrOHa) for detailed instructions on each step):
      - [Register for a free IPUMS PMA account](https://pma.ipums.org/pma/register.shtml) - give a brief description of your research interests and be sure to select **Burkina Faso** when prompted
      - [Click here](https://pma.ipums.org/pma-action/samples) to begin a new data extract by selecting samples: 
         - Select the buttons for **Longitudinal** and **Wide** format
         - Check the box for **Burkina Faso**
         - Select the button for Sample Members: **Female Respondents**
      - Next, add the following variables to your Data Cart: 
         - [RESULTFQ](https://pma.ipums.org/pma-action/variables/RESULTFQ) 
         - [PANELBIRTH](https://pma.ipums.org/pma-action/variables/PANELBIRTH)
         - [PANELWEIGHT](https://pma.ipums.org/pma-action/variables/PANELWEIGHT)
         - [EAID](https://pma.ipums.org/pma-action/variables/EAID)
         - [URBAN](https://pma.ipums.org/pma-action/variables/URBAN)
      - Follow [these instructions](https://tech.popdata.org/pma-data-hub/posts/2020-12-10-get-ipums-pma-data/index.html#fixed-width-data-format-dat) to download **both** files necessary to import the data extract into R 
         - You must download **both** the `.dat.gz` and `.xml` files 
         - Save both files into this project's `data` subfolder
  6. Open the file `ined-pma-2022.Rproj` included in this project folder
      - :rocket: this will open RStudio in a new project environment.
  7. Copy the following code into the `Console` in RStudio, then press `Enter`.
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

[Click here for slides](https://ipums-global-health.github.io/ined-pma-2022/slides.html) shown in the workshop (built with [Quarto and Revealjs](https://quarto.org/docs/presentations/revealjs/))

Source code is included in the file `analysis.Rmd`
