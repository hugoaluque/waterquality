
<!-- README.md is generated from README.Rmd. Please edit that file -->

[![CRAN
status](http://www.r-pkg.org/badges/version/waterquality)](https://cran.r-project.org/package=waterquality)
[![Build
Status](https://travis-ci.org/RAJohansen/waterquality.png?branch=master)](https://travis-ci.org/RAJohansen/waterquality)
[![codecov](https://codecov.io/gh/RAJohansen/waterquality/branch/master/graph/badge.svg)](https://codecov.io/gh/RAJohansen/waterquality)
![downloads](http://cranlogs.r-pkg.org/badges/grand-total/waterquality)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1493487.svg)](https://doi.org/10.5281/zenodo.1493487)

# waterquality

The goal of **waterquality** is to convert satellite-reflectance imagery
to a host of pre-defined water quality algorithms designed for the
detection of cholorophyll-a, blue-green algae (Phycocyanin), and
Turbidity. This package is able to process the following sensor
configurations: WorldView-2, Sentinel-2, Landsat-8, MODIS, MERIS, and OLCI.

## Installation

You can install the released version from CRAN with:

``` r
install.packages("waterquality")
```

You can install waterquality from github with:

``` r
# install.packages("devtools")
devtools::install_github("RAJohansen/waterquality")
```

## Example

The main function in this package is `wq_calc()`:

``` r
library(waterquality)
library(raster)
#> Loading required package: sp
s2 = stack(system.file("raster/S2_Harsha.tif", package = "waterquality"))
s2_two_alg = wq_calc(s2, alg = c("TurbChip09NIROverGreen", "Be16FLHGreenRedNIR"), sat = "sentinel2")
#> Be16FLHGreenRedNIR calculated!
#> TurbChip09NIROverGreen calculated!
plot(s2_two_alg)
```

![](man/figures/README-example-1.png)<!-- -->

To learn more read the [“Introduction to the waterquality
package”](https://rajohansen.github.io/waterquality/articles/waterquality_vignette.html)
vignette.

## Package Contributions

We encourage users to submit issues and enhancement requests so we may
continue to improve our package.

Futhermore, if you have a water quality algorithm that was not on our
list, and you would like for it to be included in our package please
email me at <richard.johansen@uc.edu>.
