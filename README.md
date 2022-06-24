# July 2022 INED Data Analysis Workshop 
### Linking health survey data with different climate datasets in R 
### July 6, 2022 14:00 - 16:00 (GMT+2)

Welcome! If you're looking for free registration for the in-person coding workshop, please [click here](https://www.ined.fr/en/news/scientific-meetings/seminaries-colloque-ined/population-environment-health-connecting-pixels/).

All data and software (R) featured in this workshop are available free of charge.

# 	:bangbang: Please Complete Setup Before the Workshop Begins

Setup: 

  1. [Download and Install RStudio](https://www.rstudio.com/products/rstudio/download/#download) if you do have not already done so
  2. Clone this repository, or simply click the :green_square: `Code` button on the top of this page and select `Download Zip`
  3. Once downloaded, open the file `ined-pma-2022.Rproj` 
      - :rocket: this will open RStudio in a new project environment 
  4. In the RStudio Console, run `renv::restore()`, and type `y` when prompted. 
      - :alarm_clock: it may take several minutes for this function install all of R packages we'll be using in the workshop
  5. [Register to use IPUMS PMA data](https://pma.ipums.org/pma/register.shtml)
      - :arrow_double_down:	you will need to be registered in order to **download** data during the workshop
  6. Install the spatial analysis tools [GEOS](https://libgeos.org/), [GDAL](http://www.gdal.org/), and [PRØJ](http://proj.org/) **using the appropriate instructions for your operating system**
      - **Windows:** [Install RTools](https://cran.r-project.org/bin/windows/Rtools/). All three spatial analysis tools will be included.
      - **MacOS** Follow [these instructions](https://r-spatial.github.io/sf/index.html#macos) to install [GDAL](http://www.gdal.org/) using [Homebrew](https://brew.sh/), and then continue the instructions for installing `sf` and `rgdal` in R. ([GEOS](https://libgeos.org/) and [PRØJ](http://proj.org/) will be installed automatically).
      - **Linux** Follow the appropriate instructions for your Linux distribution [shown here](https://r-spatial.github.io/sf/index.html#linux)

# Slides and Source Code

[Click here for slides]() shown in the workshop (built with [Quarto and Revealjs](https://quarto.org/docs/presentations/revealjs/))

Source code is included in the file `analysis.Rmd`
